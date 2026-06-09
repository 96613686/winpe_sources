# GEN_DTINFO::GetDllEntry(long,tagINVOKEKIND,ushort * *,ushort * *,ushort *)

- ea: `0x18005f930`
- end: `0x18005fbae`
- name: `?GetDllEntry@GEN_DTINFO@@UEAAJJW4tagINVOKEKIND@@PEAPEAG1PEAG@Z`
- size: `638`
- prototype: `int(GEN_DTINFO *__hidden this, int, enum tagINVOKEKIND, unsigned __int16 **, unsigned __int16 **, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x18000a780`
- `0x180021dc0`
- `0x18004d900`
- `0x18005b2f8`
- `0x18005f930`
- `0x18005fd90`
- `0x18005ff38`
- `0x180060550`
- `0x180061270`
- `0x18006b56c`
- `0x18006ba60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005fb7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005fb7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f9be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f9be`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fb21`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fb68`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fb21`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18005fb68`

## pseudocode

```c
__int64 __fastcall GEN_DTINFO::GetDllEntry(
        GEN_DTINFO *this,
        unsigned int a2,
        unsigned int a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 *a6)
{
  char v7; // al
  __int64 v10; // r15
  int *v11; // rcx
  int Dtmbrs; // ebx
  unsigned int v13; // eax
  __int64 v14; // r10
  unsigned int v15; // eax
  unsigned int v16; // r9d
  int v17; // r8d
  ENTRYMGR *v18; // r13
  __int64 v19; // r12
  __int64 v20; // rax
  UINT v21; // eax
  int cchWideChar; // ebx
  unsigned __int16 *lpWideCharStr; // rax
  struct DYN_TYPEMEMBERS *v26; // [rsp+38h] [rbp-C8h] BYREF
  ENTRYMGR *v27; // [rsp+40h] [rbp-C0h] BYREF
  NAMMGR *v28; // [rsp+48h] [rbp-B8h] BYREF
  CHAR MultiByteStr[256]; // [rsp+50h] [rbp-B0h] BYREF

  v26 = 0;
  v7 = a3;
  v27 = 0;
  v28 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
  {
    v7 = a3;
    *a6 = 0;
  }
  v10 = -1;
  if ( a2 != -1 && (v7 & 0xF) != 0 )
  {
    EnterCriticalSection(&g_OldFormatCriticalSection);
    v11 = (int *)*((_QWORD *)this + 7);
    if ( v11[37] < 2 )
    {
      Dtmbrs = -2147319767;
LABEL_38:
      LeaveCriticalSection(&g_OldFormatCriticalSection);
      return (unsigned int)Dtmbrs;
    }
    Dtmbrs = DYN_TYPEROOT::GetDtmbrs((DYN_TYPEROOT *)v11, &v26);
    if ( Dtmbrs < 0 )
      goto LABEL_38;
    Dtmbrs = DYN_TYPEROOT::GetEntMgr(*((DYN_TYPEROOT **)this + 7), &v27);
    if ( Dtmbrs < 0 )
      goto LABEL_38;
    Dtmbrs = DYN_TYPEROOT::GetNamMgr(*((DYN_TYPEROOT **)this + 7), &v28);
    if ( Dtmbrs < 0 )
      goto LABEL_38;
    v13 = TYPE_DATA::HfdefnOfHmember((struct DYN_TYPEMEMBERS *)((char *)v26 + 8), a2, a3);
    if ( v13 == 0xFFFF )
    {
      Dtmbrs = -2147319765;
      goto LABEL_38;
    }
    if ( *(_DWORD *)(*((_QWORD *)this + 7) + 152LL) != 2
      || (v15 = FUNC_DEFN::Hdllentrydefn((FUNC_DEFN *)(*(_QWORD *)(v14 + 8) + v13)), v15 == v17) )
    {
      Dtmbrs = -2147317571;
      goto LABEL_38;
    }
    v18 = v27;
    v19 = v15;
    if ( a4 )
    {
      Dtmbrs = NAMMGR::BstrWOfHlnam(v28, *(_WORD *)(*((_QWORD *)v27 + 2) + v15 + 2LL) & 0xFFFE, a4);
      if ( Dtmbrs )
        goto LABEL_38;
    }
    v20 = *((_QWORD *)v18 + 2);
    if ( *(_WORD *)(v19 + v20) )
    {
      if ( a6 )
        *a6 = *(_WORD *)(v19 + v20 + 4);
      if ( a5 )
        *a5 = 0;
      goto LABEL_25;
    }
    if ( a6 )
      *a6 = 0;
    if ( !a5 )
      goto LABEL_25;
    Dtmbrs = ENTRYMGR::DllEntryNameOfHchunk(
               v18,
               *(unsigned __int16 *)(v19 + *((_QWORD *)v18 + 2) + 4),
               MultiByteStr,
               v16);
    if ( !Dtmbrs )
    {
      do
        ++v10;
      while ( MultiByteStr[v10] );
      v21 = MultiByteToWideChar(0, 0, MultiByteStr, v10 + 1, 0, 0);
      cchWideChar = v21;
      if ( v21 )
      {
        lpWideCharStr = SysAllocStringLen(0, v21);
        *a5 = lpWideCharStr;
        if ( lpWideCharStr )
        {
          MultiByteToWideChar(0, 0, MultiByteStr, v10 + 1, lpWideCharStr, cchWideChar);
LABEL_25:
          Dtmbrs = 0;
          goto LABEL_38;
        }
      }
      Dtmbrs = -2147024882;
    }
    if ( a4 )
      SysFreeString(*a4);
    goto LABEL_38;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18005f930  push    rbp
0x18005f932  push    rbx
0x18005f933  push    rsi
0x18005f934  push    rdi
0x18005f935  push    r12
0x18005f937  push    r13
0x18005f939  push    r14
0x18005f93b  push    r15
0x18005f93d  lea     rbp, [rsp-68h]
0x18005f942  sub     rsp, 168h
0x18005f949  mov     rax, cs:__security_cookie
0x18005f950  xor     rax, rsp
0x18005f953  mov     [rbp+0A0h+var_50], rax
0x18005f957  mov     rsi, [rbp+0A0h+arg_20]
0x18005f95e  mov     r13, rcx
0x18005f961  mov     rdi, [rbp+0A0h+arg_28]
0x18005f968  xor     ecx, ecx
0x18005f96a  mov     [rsp+1A0h+var_168], rcx
0x18005f96f  mov     eax, r8d
0x18005f972  mov     [rsp+1A0h+var_170], eax
0x18005f976  mov     r14, r9
0x18005f979  mov     [rsp+1A0h+var_160], rcx
0x18005f97e  mov     r12d, edx
0x18005f981  mov     [rsp+1A0h+var_158], rcx
0x18005f986  test    r9, r9
0x18005f989  jz      short loc_18005F98E
0x18005f98b  mov     [r9], rcx
0x18005f98e  test    rsi, rsi
0x18005f991  jz      short loc_18005F996
0x18005f993  mov     [rsi], rcx
0x18005f996  test    rdi, rdi
0x18005f999  jz      short loc_18005F9A2
0x18005f99b  mov     eax, [rsp+1A0h+var_170]
0x18005f99f  mov     [rdi], cx
0x18005f9a2  or      r15, 0FFFFFFFFFFFFFFFFh
0x18005f9a6  cmp     r12d, r15d
0x18005f9a9  jz      loc_18005FB89
0x18005f9af  test    al, 0Fh
0x18005f9b1  jz      loc_18005FB89
0x18005f9b7  lea     rcx, ?g_OldFormatCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005f9be  call    cs:__imp_EnterCriticalSection
0x18005f9c4  mov     rcx, [r13+38h]; this
0x18005f9c8  cmp     dword ptr [rcx+94h], 2
0x18005f9cf  jge     short loc_18005F9DB
0x18005f9d1  mov     ebx, 80028029h
0x18005f9d6  jmp     loc_18005FB78
0x18005f9db  lea     rdx, [rsp+1A0h+var_168]; struct DYN_TYPEMEMBERS **
0x18005f9e0  call    ?GetDtmbrs@DYN_TYPEROOT@@UEAAJPEAPEAVDYN_TYPEMEMBERS@@@Z; DYN_TYPEROOT::GetDtmbrs(DYN_TYPEMEMBERS * *)
0x18005f9e5  mov     ebx, eax
0x18005f9e7  test    eax, eax
0x18005f9e9  js      loc_18005FB78
0x18005f9ef  mov     rcx, [r13+38h]; this
0x18005f9f3  lea     rdx, [rsp+1A0h+var_160]; struct ENTRYMGR **
0x18005f9f8  call    ?GetEntMgr@DYN_TYPEROOT@@QEAAJPEAPEAVENTRYMGR@@@Z; DYN_TYPEROOT::GetEntMgr(ENTRYMGR * *)
0x18005f9fd  mov     ebx, eax
0x18005f9ff  test    eax, eax
0x18005fa01  js      loc_18005FB78
0x18005fa07  mov     rcx, [r13+38h]; this
0x18005fa0b  lea     rdx, [rsp+1A0h+var_158]; struct NAMMGR **
0x18005fa10  call    ?GetNamMgr@DYN_TYPEROOT@@QEAAJPEAPEAVNAMMGR@@@Z; DYN_TYPEROOT::GetNamMgr(NAMMGR * *)
0x18005fa15  mov     ebx, eax
0x18005fa17  test    eax, eax
0x18005fa19  js      loc_18005FB78
0x18005fa1f  mov     r10, [rsp+1A0h+var_168]
0x18005fa24  mov     edx, r12d; unsigned int
0x18005fa27  mov     r8d, [rsp+1A0h+var_170]; unsigned int
0x18005fa2c  lea     rcx, [r10+8]; this
0x18005fa30  call    ?HfdefnOfHmember@TYPE_DATA@@QEBAIKI@Z; TYPE_DATA::HfdefnOfHmember(ulong,uint)
0x18005fa35  mov     r8d, 0FFFFh
0x18005fa3b  mov     ecx, eax
0x18005fa3d  cmp     eax, r8d
0x18005fa40  jnz     short loc_18005FA4C
0x18005fa42  mov     ebx, 8002802Bh
0x18005fa47  jmp     loc_18005FB78
0x18005fa4c  mov     rax, [r13+38h]
0x18005fa50  cmp     dword ptr [rax+98h], 2
0x18005fa57  jnz     loc_18005FB73
0x18005fa5d  add     rcx, [r10+8]; this
0x18005fa61  call    ?Hdllentrydefn@FUNC_DEFN@@QEBAIXZ; FUNC_DEFN::Hdllentrydefn(void)
0x18005fa66  cmp     eax, r8d
0x18005fa69  jz      loc_18005FB73
0x18005fa6f  mov     r13, [rsp+1A0h+var_160]
0x18005fa74  xor     ecx, ecx
0x18005fa76  mov     r12d, eax
0x18005fa79  test    r14, r14
0x18005fa7c  jz      short loc_18005FAA7
0x18005fa7e  mov     rax, [r13+10h]
0x18005fa82  mov     r8, r14; unsigned __int16 **
0x18005fa85  mov     rcx, [rsp+1A0h+var_158]; this
0x18005fa8a  movzx   edx, word ptr [rax+r12+2]
0x18005fa90  and     edx, 0FFFEh; unsigned int
0x18005fa96  call    ?BstrWOfHlnam@NAMMGR@@QEBAJIPEAPEAG@Z; NAMMGR::BstrWOfHlnam(uint,ushort * *)
0x18005fa9b  xor     ecx, ecx
0x18005fa9d  mov     ebx, eax
0x18005fa9f  test    eax, eax
0x18005faa1  jnz     loc_18005FB78
0x18005faa7  mov     rax, [r13+10h]
0x18005faab  cmp     [r12+rax], cx
0x18005fab0  jz      short loc_18005FAD1
0x18005fab2  test    rdi, rdi
0x18005fab5  jz      short loc_18005FAC0
0x18005fab7  movzx   eax, word ptr [r12+rax+4]
0x18005fabd  mov     [rdi], ax
0x18005fac0  xor     edi, edi
0x18005fac2  test    rsi, rsi
0x18005fac5  jz      short loc_18005FACA
0x18005fac7  mov     [rsi], rdi
0x18005faca  mov     ebx, edi
0x18005facc  jmp     loc_18005FB78
0x18005fad1  test    rdi, rdi
0x18005fad4  jz      short loc_18005FAD9
0x18005fad6  mov     [rdi], cx
0x18005fad9  xor     edi, edi
0x18005fadb  test    rsi, rsi
0x18005fade  jz      short loc_18005FACA
0x18005fae0  mov     rax, [r13+10h]
0x18005fae4  lea     r8, [rsp+1A0h+MultiByteStr]; char *
0x18005fae9  mov     rcx, r13; this
0x18005faec  movzx   edx, word ptr [r12+rax+4]; unsigned int
0x18005faf2  call    ?DllEntryNameOfHchunk@ENTRYMGR@@QEAAJIPEADI@Z; ENTRYMGR::DllEntryNameOfHchunk(uint,char *,uint)
0x18005faf7  mov     ebx, eax
0x18005faf9  test    eax, eax
0x18005fafb  jnz     short loc_18005FB32
0x18005fafd  lea     rax, [rsp+1A0h+MultiByteStr]
0x18005fb02  inc     r15
0x18005fb05  cmp     [rax+r15], dil
0x18005fb09  jnz     short loc_18005FB02
0x18005fb0b  mov     [rsp+1A0h+cchWideChar], edi; cchWideChar
0x18005fb0f  lea     r9d, [r15+1]; cbMultiByte
0x18005fb13  lea     r8, [rsp+1A0h+MultiByteStr]; lpMultiByteStr
0x18005fb18  mov     [rsp+1A0h+lpWideCharStr], rdi; lpWideCharStr
0x18005fb1d  xor     edx, edx; dwFlags
0x18005fb1f  xor     ecx, ecx; CodePage
0x18005fb21  call    cs:__imp_MultiByteToWideChar
0x18005fb27  mov     ebx, eax
0x18005fb29  test    eax, eax
0x18005fb2b  jnz     short loc_18005FB41
0x18005fb2d  mov     ebx, 8007000Eh
0x18005fb32  test    r14, r14
0x18005fb35  jz      short loc_18005FB78
0x18005fb37  mov     rcx, [r14]; bstrString
0x18005fb3a  call    SysFreeString
0x18005fb3f  jmp     short loc_18005FB78
0x18005fb41  mov     edx, ebx; ui
0x18005fb43  xor     ecx, ecx; strIn
0x18005fb45  call    SysAllocStringLen
0x18005fb4a  mov     [rsi], rax
0x18005fb4d  test    rax, rax
0x18005fb50  jz      short loc_18005FB2D
0x18005fb52  mov     [rsp+1A0h+cchWideChar], ebx; cchWideChar
0x18005fb56  lea     r9d, [r15+1]; cbMultiByte
0x18005fb5a  lea     r8, [rsp+1A0h+MultiByteStr]; lpMultiByteStr
0x18005fb5f  mov     [rsp+1A0h+lpWideCharStr], rax; lpWideCharStr
0x18005fb64  xor     edx, edx; dwFlags
0x18005fb66  xor     ecx, ecx; CodePage
0x18005fb68  call    cs:__imp_MultiByteToWideChar
0x18005fb6e  jmp     loc_18005FACA
0x18005fb73  mov     ebx, 800288BDh
0x18005fb78  lea     rcx, ?g_OldFormatCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18005fb7f  call    cs:__imp_LeaveCriticalSection
0x18005fb85  mov     eax, ebx
0x18005fb87  jmp     short loc_18005FB8E
0x18005fb89  mov     eax, 80070057h
0x18005fb8e  mov     rcx, [rbp+0A0h+var_50]
0x18005fb92  xor     rcx, rsp; StackCookie
0x18005fb95  call    __security_check_cookie
0x18005fb9a  add     rsp, 168h
0x18005fba1  pop     r15
0x18005fba3  pop     r14
0x18005fba5  pop     r13
0x18005fba7  pop     r12
0x18005fba9  pop     rdi
0x18005fbaa  pop     rsi
0x18005fbab  pop     rbx
0x18005fbac  pop     rbp
0x18005fbad  retn
```
