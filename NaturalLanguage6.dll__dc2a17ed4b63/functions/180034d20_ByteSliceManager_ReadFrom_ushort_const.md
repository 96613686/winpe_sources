# ByteSliceManager::ReadFrom(ushort const *)

- ea: `0x180034d20`
- end: `0x180034e0d`
- name: `?ReadFrom@ByteSliceManager@@UEAAXPEBG@Z`
- size: `237`
- prototype: `void(ByteSliceManager *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180034d20`
- `0x180035640`
- `0x18003c174`
- `0x18003ed6c`
- `0x18005d6a0`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `msvcrt!fclose` at `0x180034dd8`
- `msvcrt!fclose` at `0x180034dd8`
- `msvcrt!_wfopen` at `0x180034d71`
- `msvcrt!_wfopen` at `0x180034d71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d84`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ByteSliceManager::ReadFrom(ByteSliceManager *this, const unsigned __int16 *a2, int *a3)
{
  FILE *v5; // rax
  FILE *v6; // rbx
  signed int LastError; // eax
  int v8[4]; // [rsp+20h] [rbp-118h] BYREF
  GUID v9; // [rsp+30h] [rbp-108h] BYREF
  __int64 v10; // [rsp+40h] [rbp-F8h]
  _DWORD v11[16]; // [rsp+50h] [rbp-E8h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+90h] [rbp-A8h] BYREF
  _BYTE v13[80]; // [rsp+D0h] [rbp-68h] BYREF
  const void *retaddr; // [rsp+138h] [rbp+0h]

  v10 = -2;
  v8[0] = 0;
  CExceptionSetup::CExceptionSetup((CExceptionSetup *)v13, v8, a3);
  v5 = _wfopen(a2, L"rb");
  v6 = v5;
  *(_QWORD *)&v9.Data1 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CNLException::CNLException((CNLException *)pExceptionObject, (unsigned int)LastError, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  try
  {
    (*(void (__fastcall **)(ByteSliceManager *, FILE *))(*(_QWORD *)this + 32LL))(this, v5);
  }
  catch ( CNLException v11 )
  {
    fclose(*(FILE **)&v9.Data1);
    ImxTraceCatch(0, v11[2], retaddr);
    v9 = GUID_NULL;
    CNLException::HandleIt((CNLException *)v11, (struct CExceptionSetup *)v13, &v9);
    CNLException::Throw((CNLException *)v11);
  }
  fclose(v6);
  CExceptionSetup::~CExceptionSetup((CExceptionSetup *)v13);
}

```

## disassembly

```asm
0x180034d20  mov     r11, rsp
0x180034d23  push    rdi
0x180034d24  sub     rsp, 130h
0x180034d2b  mov     [rsp+138h+var_F8], 0FFFFFFFFFFFFFFFEh
0x180034d34  mov     [r11+18h], rbx
0x180034d38  mov     rax, cs:__security_cookie
0x180034d3f  xor     rax, rsp
0x180034d42  mov     [rsp+138h+var_18], rax
0x180034d4a  mov     rbx, rdx
0x180034d4d  mov     rdi, rcx
0x180034d50  mov     [rsp+138h+var_118], 0
0x180034d58  lea     rdx, [rsp+138h+var_118]; int *
0x180034d5d  lea     rcx, [r11-68h]; this
0x180034d61  call    ??0CExceptionSetup@@QEAA@PEAJPEAH@Z; CExceptionSetup::CExceptionSetup(long *,int *)
0x180034d66  nop
0x180034d67  lea     rdx, aRb; "rb"
0x180034d6e  mov     rcx, rbx; FileName
0x180034d71  call    cs:__imp__wfopen
0x180034d77  mov     rbx, rax
0x180034d7a  mov     qword ptr [rsp+138h+var_108], rax
0x180034d7f  test    rax, rax
0x180034d82  jnz     short loc_180034DC2
0x180034d84  call    cs:__imp_GetLastError
0x180034d8a  test    eax, eax
0x180034d8c  jle     short loc_180034D96
0x180034d8e  movzx   eax, ax
0x180034d91  or      eax, 80070000h
0x180034d96  mov     r8, [rsp+138h]; void *
0x180034d9e  mov     edx, eax; int
0x180034da0  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180034da8  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x180034dad  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x180034db4  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180034dbc  call    _CxxThrowException_0
0x180034dc2  mov     rax, [rdi]
0x180034dc5  mov     rdx, rbx
0x180034dc8  mov     rcx, rdi
0x180034dcb  mov     rax, [rax+20h]
0x180034dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034dd4  nop
0x180034dd5  mov     rcx, rbx; Stream
0x180034dd8  call    cs:__imp_fclose
0x180034dde  nop
0x180034ddf  lea     rcx, [rsp+138h+var_68]; this
0x180034de7  call    ??1CExceptionSetup@@QEAA@XZ; CExceptionSetup::~CExceptionSetup(void)
0x180034dec  mov     rcx, [rsp+138h+var_18]
0x180034df4  xor     rcx, rsp; StackCookie
0x180034df7  call    __security_check_cookie
0x180034dfc  mov     rbx, [rsp+138h+arg_10]
0x180034e04  add     rsp, 130h
0x180034e0b  pop     rdi
0x180034e0c  retn
```
