# InitializeLogEx(wchar_t const *,wchar_t const *)

- ea: `0x140023d3c`
- end: `0x140023e7f`
- name: `?InitializeLogEx@@YAXPEB_W0@Z`
- size: `323`
- prototype: `void(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001d700`

## callees

- `0x140005c40`
- `0x140005da0`
- `0x1400234b0`
- `0x1400235e4`
- `0x140023b94`
- `0x140023d3c`
- `0x140024148`
- `0x140024614`
- `0x140024cc0`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x140023e20`
- `MpClient!MpFreeMemory` at `0x140023e20`
- `KERNEL32!GetCommandLineW` at `0x140023df9`
- `KERNEL32!GetCommandLineW` at `0x140023df9`

## string_xrefs

- `0x140023e05`: `MpCopyAccelerator`
- `0x140023e58`: `MpCopyAccelerator`
- `0x140023e0c`: `%s: Command Line: %s\n Start Time: %s\n\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall InitializeLogEx(const wchar_t *a1, const wchar_t *a2)
{
  const wchar_t *v3; // rdx
  bool v4; // r9
  CLogHandle *v5; // rax
  CLogHandle *v6; // rbx
  const wchar_t *v7; // rdi
  void *v8; // rbx
  LPWSTR CommandLineW; // rax
  __int64 v10; // [rsp+0h] [rbp-58h] BYREF
  char v11[8]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-20h]
  const std::exception *v13; // [rsp+40h] [rbp-18h] BYREF

  v12 = (__int64)a2;
  if ( qword_14003DBC8 )
    return;
  try
  {
    *(_QWORD *)v11 = operator new(0x48u);
    memset(*(void **)v11, 0, 0x48u);
    v5 = CLogHandle::CLogHandle(*(CLogHandle **)v11, v3, a2, v4);
    v6 = qword_14003DBC8;
    qword_14003DBC8 = v5;
    if ( v6 )
    {
      CLogHandle::~CLogHandle(v6);
      operator delete(v6, 0x48u);
    }
  }
  catch ( const std::exception *v13 )
  {
    CommonUtil::HrFromStdException(v13, (const struct std::exception *)&v10);
  }
  catch ( ... )
  {
    *(_DWORD *)v11 = -2147467259;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, v11[0]);
    return;
  }
  *(_QWORD *)v11 = 0;
  GetTime(v11, 0);
  MpCmdLogPrintf(L"%S", "\n\n-------------------------------------------------------------------------------------\n");
  v7 = L" ";
  v8 = *(void **)v11;
  if ( *(_QWORD *)v11 )
    v7 = *(const wchar_t **)v11;
  CommandLineW = GetCommandLineW();
  MpCmdLogPrintf(L"%s: Command Line: %s\n Start Time: %s\n\n", L"MpCopyAccelerator", CommandLineW, v7);
  if ( v8 )
    MpFreeMemory(v8);
}

```

## disassembly

```asm
0x140023d3c  mov     [rsp+arg_0], rbx
0x140023d41  mov     [rsp+arg_10], rsi
0x140023d46  push    rdi
0x140023d47  sub     rsp, 50h
0x140023d4b  mov     rdi, rdx
0x140023d4e  mov     [rsp+58h+var_20], rdx
0x140023d53  cmp     cs:qword_14003DBC8, 0
0x140023d5b  jnz     loc_140023E6F
0x140023d61  mov     esi, 48h ; 'H'
0x140023d66  mov     ecx, esi; Size
0x140023d68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140023d6d  mov     rbx, rax
0x140023d70  mov     qword ptr [rsp+58h+var_28], rax
0x140023d75  mov     r8d, esi; Size
0x140023d78  xor     edx, edx; Val
0x140023d7a  mov     rcx, rax; void *
0x140023d7d  call    memset
0x140023d82  mov     r8, rdi; wchar_t *
0x140023d85  mov     rcx, rbx; this
0x140023d88  call    ??0CLogHandle@@QEAA@PEB_W0_N@Z; CLogHandle::CLogHandle(wchar_t const *,wchar_t const *,bool)
0x140023d8d  nop
0x140023d8e  mov     rbx, cs:qword_14003DBC8
0x140023d95  mov     cs:qword_14003DBC8, rax
0x140023d9c  test    rbx, rbx
0x140023d9f  jz      short loc_140023DB4
0x140023da1  mov     rcx, rbx; this
0x140023da4  call    ??1CLogHandle@@QEAA@XZ; CLogHandle::~CLogHandle(void)
0x140023da9  mov     edx, esi; unsigned __int64
0x140023dab  mov     rcx, rbx; void *
0x140023dae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140023db3  nop
0x140023db4  jmp     short loc_140023DBE
0x140023db6  mov     eax, dword ptr [rsp+58h+var_28]
0x140023dba  test    eax, eax
0x140023dbc  js      short loc_140023E2C
0x140023dbe  mov     qword ptr [rsp+58h+var_28], 0
0x140023dc7  xor     edx, edx
0x140023dc9  lea     rcx, [rsp+58h+var_28]
0x140023dce  call    GetTime
0x140023dd3  lea     rdx, asc_1400356A0; "\n\n-----------------------------------"...
0x140023dda  lea     rcx, aS_0; "%S"
0x140023de1  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x140023de6  lea     rdi, asc_140035704; " "
0x140023ded  mov     rbx, qword ptr [rsp+58h+var_28]
0x140023df2  test    rbx, rbx
0x140023df5  cmovnz  rdi, rbx
0x140023df9  call    cs:__imp_GetCommandLineW
0x140023dff  mov     r9, rdi
0x140023e02  mov     r8, rax
0x140023e05  lea     rdx, aMpcopyaccelera_3; "MpCopyAccelerator"
0x140023e0c  lea     rcx, aSCommandLineSS; "%s: Command Line: %s\n Start Time: %s\n"...
0x140023e13  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x140023e18  test    rbx, rbx
0x140023e1b  jz      short loc_140023E6F
0x140023e1d  mov     rcx, rbx
0x140023e20  call    cs:__imp_MpFreeMemory
0x140023e26  jmp     short loc_140023E6F
0x140023e28  mov     eax, dword ptr [rsp+58h+var_28]
0x140023e2c  lea     rdx, WPP_GLOBAL_Control
0x140023e33  mov     rcx, cs:WPP_GLOBAL_Control
0x140023e3a  cmp     rcx, rdx
0x140023e3d  jz      short loc_140023E6F
0x140023e3f  test    byte ptr [rcx+1Ch], 1
0x140023e43  jz      short loc_140023E6F
0x140023e45  mov     edx, 19h
0x140023e4a  mov     dword ptr [rsp+58h+var_30], eax; char
0x140023e4e  mov     rax, [rsp+58h+var_20]
0x140023e53  mov     [rsp+58h+var_38], rax; __int64
0x140023e58  lea     r9, aMpcopyaccelera_3; "MpCopyAccelerator"
0x140023e5f  lea     r8, WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids
0x140023e66  mov     rcx, [rcx+10h]; LoggerHandle
0x140023e6a  call    WPP_SF_SSd
0x140023e6f  mov     rbx, [rsp+58h+arg_0]
0x140023e74  mov     rsi, [rsp+58h+arg_10]
0x140023e79  add     rsp, 50h
0x140023e7d  pop     rdi
0x140023e7e  retn
```
