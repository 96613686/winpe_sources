# CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)

- ea: `0x140015240`
- end: `0x1400153cc`
- name: `?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z`
- size: `396`
- prototype: `__int64 __fastcall(CEventLogger *this, const struct _EVENT_DESCRIPTOR *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `45`
- callee_count: `5`
- tags: ``

## callers

- `0x14000dd80`
- `0x14000ded0`
- `0x14000e0e0`
- `0x14000e904`
- `0x14000eb50`
- `0x14000ed54`
- `0x14000eef0`
- `0x14000efc0`
- `0x14000f2c8`
- `0x14000f458`
- `0x14000f9ac`
- `0x14000fc0c`
- `0x14000fcf4`
- `0x14000fd90`
- `0x14000ff18`
- `0x140010178`
- `0x140010594`
- `0x140010868`
- `0x140010ca4`
- `0x140010dc4`
- `0x1400111c8`
- `0x140011530`
- `0x1400117e0`
- `0x140011ab0`
- `0x140011d10`
- `0x140011fc0`
- `0x140012890`
- `0x140012c00`
- `0x140012e70`
- `0x140012f10`
- `0x140012fe0`
- `0x140013250`
- `0x140013760`
- `0x140013a88`
- `0x140013c10`
- `0x140013ef8`
- `0x140014388`
- `0x140014508`
- `0x140014618`
- `0x140014740`
- `0x140014894`
- `0x140014a90`
- `0x140014ccc`
- `0x140014f10`
- `0x1400156c8`

## callees

- `0x1400022d3`
- `0x14000aafc`
- `0x140011394`
- `0x140015240`
- `0x140015aa0`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x140015394`
- `ADVAPI32!EventWrite` at `0x140015394`
- `KERNEL32!GetLastError` at `0x1400152d4`
- `KERNEL32!GetLastError` at `0x1400152d4`

## pseudocode

```c
__int64 __fastcall CEventLogger::LogError(
        CEventLogger *this,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned int a6)
{
  DWORD LastError; // eax
  unsigned int v9; // r11d
  __int64 v11; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v12; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v15; // [rsp+50h] [rbp-B0h]
  __int64 v16; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+68h] [rbp-98h]
  int v19; // [rsp+6Ch] [rbp-94h]
  unsigned int *v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+78h] [rbp-88h]
  unsigned __int16 v22[128]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v23[128]; // [rsp+180h] [rbp+80h] BYREF

  v12 = 0;
  LODWORD(v11) = a4;
  v13 = 0;
  memset_0(v22, 0, sizeof(v22));
  memset_0(v23, 0, sizeof(v23));
  StringCchPrintfW(v22, 0x80u, L"%d", a4, v11);
  LastError = a6;
  if ( !a6 )
  {
    LastError = GetLastError();
    a6 = LastError;
  }
  StringCchPrintfW(v23, 0x80u, L"%x", LastError);
  if ( (int)StringCbLengthW(a3, 0xFFFFFFFE, &v12) < 0 || (int)StringCbLengthW(a5, v9, &v13) < 0 )
    return 2147500037LL;
  UserData.Ptr = (ULONGLONG)a3;
  UserData.Size = v12 + 2;
  UserData.Reserved = 0;
  v15 = &v11;
  v16 = 4;
  v18 = v13 + 2;
  v20 = &a6;
  v17 = a5;
  v19 = 0;
  v21 = 4;
  return EventWrite(g_Logger, &Recoverable_Error, 4u, &UserData) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x140015240  mov     [rsp-8+arg_0], rbx
0x140015245  push    rbp
0x140015246  push    rsi
0x140015247  push    rdi
0x140015248  lea     rbp, [rsp-190h]
0x140015250  sub     rsp, 290h
0x140015257  mov     rax, cs:__security_cookie
0x14001525e  xor     rax, rsp
0x140015261  mov     [rbp+1A0h+var_20], rax
0x140015268  mov     rdi, [rbp+1A0h+arg_20]
0x14001526f  lea     rcx, [rbp+1A0h+var_220]; void *
0x140015273  mov     ebx, r9d
0x140015276  mov     [rsp+2A0h+var_278], 0
0x14001527f  mov     rsi, r8
0x140015282  mov     dword ptr [rsp+2A0h+var_280], ebx
0x140015286  mov     r8d, 100h; Size
0x14001528c  mov     [rsp+2A0h+var_270], 0
0x140015295  xor     edx, edx; Val
0x140015297  call    memset_0
0x14001529c  xor     edx, edx; Val
0x14001529e  lea     rcx, [rbp+1A0h+var_120]; void *
0x1400152a5  mov     r8d, 100h; Size
0x1400152ab  call    memset_0
0x1400152b0  mov     r9d, ebx
0x1400152b3  lea     r8, aD; "%d"
0x1400152ba  mov     ebx, 80h
0x1400152bf  lea     rcx, [rbp+1A0h+var_220]; unsigned __int16 *
0x1400152c3  mov     edx, ebx; unsigned __int64
0x1400152c5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400152ca  mov     eax, [rbp+1A0h+arg_28]
0x1400152d0  test    eax, eax
0x1400152d2  jnz     short loc_1400152E0
0x1400152d4  call    cs:__imp_GetLastError
0x1400152da  mov     [rbp+1A0h+arg_28], eax
0x1400152e0  mov     r9d, eax
0x1400152e3  lea     r8, asc_14001CBA0; "%x"
0x1400152ea  mov     rdx, rbx; unsigned __int64
0x1400152ed  lea     rcx, [rbp+1A0h+var_120]; unsigned __int16 *
0x1400152f4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400152f9  mov     r11d, 0FFFFFFFEh
0x1400152ff  lea     r8, [rsp+2A0h+var_278]; unsigned __int64 *
0x140015304  mov     edx, r11d; unsigned __int64
0x140015307  mov     rcx, rsi; unsigned __int16 *
0x14001530a  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001530f  test    eax, eax
0x140015311  js      loc_1400153A5
0x140015317  lea     r8, [rsp+2A0h+var_270]; unsigned __int64 *
0x14001531c  mov     edx, r11d; unsigned __int64
0x14001531f  mov     rcx, rdi; unsigned __int16 *
0x140015322  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140015327  test    eax, eax
0x140015329  js      short loc_1400153A5
0x14001532b  mov     eax, dword ptr [rsp+2A0h+var_278]
0x14001532f  lea     r9, [rsp+2A0h+UserData]; UserData
0x140015334  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x14001533b  lea     rdx, Recoverable_Error; EventDescriptor
0x140015342  add     eax, 2
0x140015345  mov     [rsp+2A0h+UserData.Ptr], rsi
0x14001534a  mov     [rsp+2A0h+UserData.Size], eax
0x14001534e  mov     r8d, 4; UserDataCount
0x140015354  lea     rax, [rsp+2A0h+var_280]
0x140015359  mov     dword ptr [rsp+2A0h+UserData.0Ch], 0
0x140015361  mov     [rsp+2A0h+var_250], rax
0x140015366  mov     eax, dword ptr [rsp+2A0h+var_270]
0x14001536a  add     eax, 2
0x14001536d  mov     [rsp+2A0h+var_248], r8
0x140015372  mov     [rsp+2A0h+var_238], eax
0x140015376  lea     rax, [rbp+1A0h+arg_28]
0x14001537d  mov     [rsp+2A0h+var_230], rax
0x140015382  mov     [rsp+2A0h+var_240], rdi
0x140015387  mov     [rsp+2A0h+var_234], 0
0x14001538f  mov     [rsp+2A0h+var_228], r8
0x140015394  call    cs:__imp_EventWrite
0x14001539a  neg     eax
0x14001539c  sbb     eax, eax
0x14001539e  and     eax, 80004005h
0x1400153a3  jmp     short loc_1400153AA
0x1400153a5  mov     eax, 80004005h
0x1400153aa  mov     rcx, [rbp+1A0h+var_20]
0x1400153b1  xor     rcx, rsp; StackCookie
0x1400153b4  call    __security_check_cookie
0x1400153b9  mov     rbx, [rsp+2A0h+arg_0]
0x1400153c1  add     rsp, 290h
0x1400153c8  pop     rdi
0x1400153c9  pop     rsi
0x1400153ca  pop     rbp
0x1400153cb  retn
```
