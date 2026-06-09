# GetNumInfo(ulong,ulong,tagNUMINFO * *)

- ea: `0x1800057e0`
- end: `0x18000597f`
- name: `?GetNumInfo@@YAJKKPEAPEAUtagNUMINFO@@@Z`
- size: `415`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct tagNUMINFO **)`
- caller_count: `10`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180003ee0`
- `0x180026620`
- `0x180027ef0`
- `0x180035810`
- `0x180035940`
- `0x180036a40`
- `0x180038550`
- `0x180071b48`
- `0x180077cd0`
- `0x180077e60`

## callees

- `0x1800039b8`
- `0x1800057e0`
- `0x180005988`
- `0x18000705c`
- `0x180048bf8`
- `0x18004a8f4`
- `0x18004d924`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800058a9`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800058a9`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800058ff`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x1800058ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005839`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005918`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005839`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005918`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18000587a`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18000587a`

## pseudocode

```c
__int64 __fastcall GetNumInfo(unsigned int a1, int a2, struct tagNUMINFO **a3)
{
  char *v3; // r14
  unsigned int v6; // esi
  signed int v7; // ebp
  unsigned __int64 v8; // rdx
  LPVOID Value; // r13
  char **v10; // rbx
  int v11; // edi
  LCID UserDefaultLCID; // eax
  unsigned __int64 v14; // rdx
  int inited; // ebx
  CNumInfo *v16; // rcx
  struct CNumInfo *v17; // rcx
  char *v18; // [rsp+60h] [rbp+18h] BYREF
  struct CNumInfo *v19; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  *a3 = 0;
  v18 = 0;
  v6 = a1;
  if ( g_bPerUserNlsCache )
  {
    if ( a2 == 0x80000000 && a1 == 1033 )
      goto LABEL_4;
    GetUserInfo(&v18);
    v3 = v18;
  }
  if ( v6 == 1024 )
  {
    UserDefaultLCID = GetUserDefaultLCID();
  }
  else
  {
    if ( v6 != 2048 )
      goto LABEL_4;
    UserDefaultLCID = GetSystemDefaultLCID();
  }
  v6 = UserDefaultLCID;
LABEL_4:
  v7 = g_dwProcessNlsFlags | a2;
  Value = TlsGetValue(g_itlsAppData);
  if ( !Value )
  {
    inited = InitAppData();
    if ( inited < 0 )
      goto LABEL_18;
    Value = TlsGetValue(g_itlsAppData);
  }
  v10 = (char **)*((_QWORD *)Value + 51);
  v19 = (struct CNumInfo *)v10;
  if ( v10 && *((_DWORD *)v10 + 4) == v6 && *((_DWORD *)v10 + 5) == v7 && (!v3 || (unsigned int)IsSameUser(v3, v10[1])) )
  {
    if ( v7 < 0 || (v11 = *(_DWORD *)v10, v11 == (unsigned int)NlsGetCacheUpdateCount()) )
    {
      if ( v3 )
        operator delete(v3, v8);
      *a3 = (struct tagNUMINFO *)v10;
      return 0;
    }
  }
  inited = CNumInfo::Create(v6, v7, &v19, &v18);
  if ( inited >= 0 )
  {
    v16 = (CNumInfo *)*((_QWORD *)Value + 51);
    if ( v16 )
      CNumInfo::Release(v16);
    v17 = v19;
    *((_QWORD *)Value + 51) = v19;
    *a3 = v17;
  }
  v3 = v18;
LABEL_18:
  if ( v3 )
    operator delete(v3, v14);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800057e0  push    rbp
0x1800057e2  push    rsi
0x1800057e3  push    r13
0x1800057e5  push    r14
0x1800057e7  push    r15
0x1800057e9  sub     rsp, 20h
0x1800057ed  xor     r14d, r14d
0x1800057f0  mov     qword ptr [r8], 0
0x1800057f7  cmp     cs:?g_bPerUserNlsCache@@3KA, r14d; ulong g_bPerUserNlsCache
0x1800057fe  mov     r15, r8
0x180005801  mov     ebp, edx
0x180005803  mov     [rsp+48h+arg_10], r14
0x180005808  mov     esi, ecx
0x18000580a  jnz     loc_180005956
0x180005810  cmp     esi, 400h
0x180005816  jz      loc_1800058A9
0x18000581c  cmp     esi, 800h
0x180005822  jz      loc_1800058FF
0x180005828  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x18000582e  or      ebp, cs:?g_dwProcessNlsFlags@@3KA; ulong g_dwProcessNlsFlags
0x180005834  mov     [rsp+48h+arg_0], rbx
0x180005839  call    cs:__imp_TlsGetValue
0x18000583f  mov     r13, rax
0x180005842  test    rax, rax
0x180005845  jz      loc_180005907
0x18000584b  mov     rbx, [r13+198h]
0x180005852  mov     [rsp+48h+arg_18], rbx
0x180005857  test    rbx, rbx
0x18000585a  jz      short loc_1800058B6
0x18000585c  cmp     [rbx+10h], esi
0x18000585f  jnz     short loc_1800058B6
0x180005861  cmp     [rbx+14h], ebp
0x180005864  jnz     short loc_1800058B6
0x180005866  test    r14, r14
0x180005869  jnz     loc_18000593D
0x18000586f  test    ebp, ebp
0x180005871  js      short loc_180005889
0x180005873  mov     [rsp+48h+arg_8], rdi
0x180005878  mov     edi, [rbx]
0x18000587a  call    cs:__imp_NlsGetCacheUpdateCount
0x180005880  cmp     edi, eax
0x180005882  mov     rdi, [rsp+48h+arg_8]
0x180005887  jnz     short loc_1800058B6
0x180005889  test    r14, r14
0x18000588c  jnz     loc_180005930
0x180005892  mov     [r15], rbx
0x180005895  xor     eax, eax
0x180005897  mov     rbx, [rsp+48h+arg_0]
0x18000589c  add     rsp, 20h
0x1800058a0  pop     r15
0x1800058a2  pop     r14
0x1800058a4  pop     r13
0x1800058a6  pop     rsi
0x1800058a7  pop     rbp
0x1800058a8  retn
0x1800058a9  call    cs:__imp_GetUserDefaultLCID
0x1800058af  mov     esi, eax
0x1800058b1  jmp     loc_180005828
0x1800058b6  lea     r9, [rsp+48h+arg_10]; char **
0x1800058bb  mov     edx, ebp; unsigned int
0x1800058bd  lea     r8, [rsp+48h+arg_18]; struct CNumInfo **
0x1800058c2  mov     ecx, esi; unsigned int
0x1800058c4  call    ?Create@CNumInfo@@SAJKKPEAPEAV1@PEAPEAD@Z; CNumInfo::Create(ulong,ulong,CNumInfo * *,char * *)
0x1800058c9  mov     ebx, eax
0x1800058cb  test    eax, eax
0x1800058cd  jns     short loc_1800058DD
0x1800058cf  mov     r14, [rsp+48h+arg_10]
0x1800058d4  test    r14, r14
0x1800058d7  jnz     short loc_180005926
0x1800058d9  mov     eax, ebx
0x1800058db  jmp     short loc_180005897
0x1800058dd  mov     rcx, [r13+198h]; this
0x1800058e4  test    rcx, rcx
0x1800058e7  jz      short loc_1800058EE
0x1800058e9  call    ?Release@CNumInfo@@QEAAKXZ; CNumInfo::Release(void)
0x1800058ee  mov     rcx, [rsp+48h+arg_18]
0x1800058f3  mov     [r13+198h], rcx
0x1800058fa  mov     [r15], rcx
0x1800058fd  jmp     short loc_1800058CF
0x1800058ff  call    cs:__imp_GetSystemDefaultLCID
0x180005905  jmp     short loc_1800058AF
0x180005907  call    InitAppData
0x18000590c  mov     ebx, eax
0x18000590e  test    eax, eax
0x180005910  js      short loc_1800058D4
0x180005912  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x180005918  call    cs:__imp_TlsGetValue
0x18000591e  mov     r13, rax
0x180005921  jmp     loc_18000584B
0x180005926  mov     rcx, r14; void *
0x180005929  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000592e  jmp     short loc_1800058D9
0x180005930  mov     rcx, r14; void *
0x180005933  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005938  jmp     loc_180005892
0x18000593d  mov     rdx, [rbx+8]; char *
0x180005941  mov     rcx, r14; char *
0x180005944  call    ?IsSameUser@@YAHPEAD0@Z; IsSameUser(char *,char *)
0x180005949  test    eax, eax
0x18000594b  jnz     loc_18000586F
0x180005951  jmp     loc_1800058B6
0x180005956  cmp     ebp, 80000000h
0x18000595c  jz      short loc_180005972
0x18000595e  lea     rcx, [rsp+48h+arg_10]; char **
0x180005963  call    ?GetUserInfo@@YAXPEAPEAD@Z; GetUserInfo(char * *)
0x180005968  mov     r14, [rsp+48h+arg_10]
0x18000596d  jmp     loc_180005810
0x180005972  cmp     esi, 409h
0x180005978  jnz     short loc_18000595E
0x18000597a  jmp     loc_180005828
```
