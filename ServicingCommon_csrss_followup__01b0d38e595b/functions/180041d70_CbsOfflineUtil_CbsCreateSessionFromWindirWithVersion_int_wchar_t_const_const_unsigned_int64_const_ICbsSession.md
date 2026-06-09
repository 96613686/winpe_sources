# CbsOfflineUtil::CbsCreateSessionFromWindirWithVersion(int,wchar_t const * const,unsigned __int64 const *,ICbsSession * *)

- ea: `0x180041d70`
- end: `0x180041f19`
- name: `?CbsCreateSessionFromWindirWithVersion@CbsOfflineUtil@@UEAAJHQEB_WPEB_KPEAPEAUICbsSession@@@Z`
- size: `425`
- prototype: `__int64 __usercall@<rax>(CbsOfflineUtil *__hidden this@<rcx>, int@<edx>, const wchar_t *const@<r8>, const unsigned __int64 *@<r9>, struct ICbsSession **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002d2b0`
- `0x180040f00`
- `0x180041d70`
- `0x180042bac`
- `0x180097e20`
- `0x18009e020`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180041df8`
- `KERNEL32!GetLastError` at `0x180041df8`
- `KERNEL32!GetProcessHeap` at `0x180041eb8`
- `KERNEL32!GetProcessHeap` at `0x180041eb8`
- `KERNEL32!HeapFree` at `0x180041ecc`
- `KERNEL32!HeapFree` at `0x180041ecc`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180041de8`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180041de8`

## string_xrefs

- `0x180041e40`: `cbscore.dll`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsCreateSessionFromWindirWithVersion(
        CbsOfflineUtil *this,
        unsigned int a2,
        WCHAR *a3,
        const unsigned __int64 *a4,
        struct ICbsSession **a5)
{
  UINT SystemWindowsDirectoryW; // eax
  signed int LastError; // eax
  int SessionFromCbsCorePath; // ebx
  struct ICbsSession **InitPointer; // rax
  void *v13; // rdi
  HANDLE ProcessHeap; // rax
  struct ICbsSession *v16; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  v16 = 0;
  lpMem = 0;
  *a5 = 0;
  memset(Buffer, 0, 0x208u);
  if ( !a3 )
  {
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
    if ( !SystemWindowsDirectoryW )
    {
      LastError = GetLastError();
      SessionFromCbsCorePath = LastError;
      if ( LastError > 0 )
        SessionFromCbsCorePath = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_11;
    }
    if ( SystemWindowsDirectoryW >= 0x104 )
    {
      SessionFromCbsCorePath = -2147024774;
      goto LABEL_11;
    }
    a3 = Buffer;
  }
  SessionFromCbsCorePath = (*(__int64 (__fastcall **)(CbsOfflineUtil *, _QWORD, WCHAR *, const wchar_t *, const unsigned __int64 *, _QWORD, _QWORD, LPVOID *, _QWORD))(*(_QWORD *)this + 64LL))(
                             this,
                             a2,
                             a3,
                             L"cbscore.dll",
                             a4,
                             0,
                             0,
                             &lpMem,
                             0);
  if ( SessionFromCbsCorePath >= 0 )
  {
    InitPointer = (struct ICbsSession **)Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(&v16);
    SessionFromCbsCorePath = CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(this, (const wchar_t *)lpMem, InitPointer);
    if ( SessionFromCbsCorePath >= 0 )
    {
      SessionFromCbsCorePath = 0;
      *a5 = v16;
      v16 = 0;
    }
  }
LABEL_11:
  v13 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v13);
    lpMem = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(struct ICbsSession *))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)SessionFromCbsCorePath;
}

```

## disassembly

```asm
0x180041d70  push    rbp
0x180041d72  push    rbx
0x180041d73  push    rsi
0x180041d74  push    rdi
0x180041d75  push    r14
0x180041d77  push    r15
0x180041d79  lea     rbp, [rsp-188h]
0x180041d81  sub     rsp, 288h
0x180041d88  mov     rax, cs:__security_cookie
0x180041d8f  xor     rax, rsp
0x180041d92  mov     [rbp+1B0h+var_40], rax
0x180041d99  mov     rdi, [rbp+1B0h+arg_20]
0x180041da0  mov     rbx, r8
0x180041da3  mov     r14d, edx
0x180041da6  mov     [rsp+2B0h+var_260], 0
0x180041daf  mov     rsi, rcx
0x180041db2  mov     [rsp+2B0h+lpMem], 0
0x180041dbb  xor     edx, edx; Val
0x180041dbd  lea     rcx, [rsp+2B0h+Buffer]; void *
0x180041dc2  mov     r8d, 208h; Size
0x180041dc8  mov     qword ptr [rdi], 0
0x180041dcf  mov     r15, r9
0x180041dd2  call    memset
0x180041dd7  test    rbx, rbx
0x180041dda  jnz     short loc_180041E2F
0x180041ddc  mov     ebx, 104h
0x180041de1  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x180041de6  mov     edx, ebx; uSize
0x180041de8  call    cs:__imp_GetSystemWindowsDirectoryW
0x180041def  nop     dword ptr [rax+rax+00h]
0x180041df4  test    eax, eax
0x180041df6  jnz     short loc_180041E1C
0x180041df8  call    cs:__imp_GetLastError
0x180041dff  nop     dword ptr [rax+rax+00h]
0x180041e04  mov     ebx, eax
0x180041e06  test    eax, eax
0x180041e08  jle     loc_180041EAE
0x180041e0e  movzx   ebx, ax
0x180041e11  or      ebx, 80070000h
0x180041e17  jmp     loc_180041EAE
0x180041e1c  cmp     eax, ebx
0x180041e1e  jb      short loc_180041E2A
0x180041e20  mov     ebx, 8007007Ah
0x180041e25  jmp     loc_180041EAE
0x180041e2a  lea     rbx, [rsp+2B0h+Buffer]
0x180041e2f  mov     rax, [rsi]
0x180041e32  lea     rcx, [rsp+2B0h+lpMem]
0x180041e37  mov     [rsp+2B0h+var_270], 0
0x180041e40  lea     r9, aCbscoreDll_0; "cbscore.dll"
0x180041e47  mov     [rsp+2B0h+var_278], rcx
0x180041e4c  mov     r8, rbx
0x180041e4f  mov     [rsp+2B0h+var_280], 0
0x180041e58  mov     edx, r14d
0x180041e5b  mov     rax, [rax+40h]
0x180041e5f  mov     rcx, rsi
0x180041e62  mov     [rsp+2B0h+var_288], 0
0x180041e6b  mov     [rsp+2B0h+var_290], r15
0x180041e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e75  mov     ebx, eax
0x180041e77  test    eax, eax
0x180041e79  js      short loc_180041EAE
0x180041e7b  lea     rcx, [rsp+2B0h+var_260]
0x180041e80  call    ?GetInitPointer@?$AutoComPtr@UICbsIdentity@@@Windows@@QEAAPEAPEAUICbsIdentity@@XZ; Windows::AutoComPtr<ICbsIdentity>::GetInitPointer(void)
0x180041e85  mov     rdx, [rsp+2B0h+lpMem]; wchar_t *
0x180041e8a  mov     r8, rax; struct ICbsSession **
0x180041e8d  mov     rcx, rsi; this
0x180041e90  call    ?CbsCreateSessionFromCbsCorePath@CbsOfflineUtil@@QEAAJPEB_WPEAPEAUICbsSession@@@Z; CbsOfflineUtil::CbsCreateSessionFromCbsCorePath(wchar_t const *,ICbsSession * *)
0x180041e95  mov     ebx, eax
0x180041e97  test    eax, eax
0x180041e99  js      short loc_180041EAE
0x180041e9b  mov     rax, [rsp+2B0h+var_260]
0x180041ea0  xor     ebx, ebx
0x180041ea2  mov     [rdi], rax
0x180041ea5  mov     [rsp+2B0h+var_260], 0
0x180041eae  mov     rdi, [rsp+2B0h+lpMem]
0x180041eb3  test    rdi, rdi
0x180041eb6  jz      short loc_180041EE1
0x180041eb8  call    cs:__imp_GetProcessHeap
0x180041ebf  nop     dword ptr [rax+rax+00h]
0x180041ec4  mov     r8, rdi; lpMem
0x180041ec7  xor     edx, edx; dwFlags
0x180041ec9  mov     rcx, rax; hHeap
0x180041ecc  call    cs:__imp_HeapFree
0x180041ed3  nop     dword ptr [rax+rax+00h]
0x180041ed8  mov     [rsp+2B0h+lpMem], 0
0x180041ee1  mov     rcx, [rsp+2B0h+var_260]
0x180041ee6  test    rcx, rcx
0x180041ee9  jz      short loc_180041EF7
0x180041eeb  mov     rax, [rcx]
0x180041eee  mov     rax, [rax+10h]
0x180041ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ef7  mov     eax, ebx
0x180041ef9  mov     rcx, [rbp+1B0h+var_40]
0x180041f00  xor     rcx, rsp; StackCookie
0x180041f03  call    __security_check_cookie
0x180041f08  add     rsp, 288h
0x180041f0f  pop     r15
0x180041f11  pop     r14
0x180041f13  pop     rdi
0x180041f14  pop     rsi
0x180041f15  pop     rbx
0x180041f16  pop     rbp
0x180041f17  retn
```
