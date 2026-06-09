# sub_180D8CCD4

- ea: `0x180d8ccd4`
- end: `0x180d8d116`
- name: `sub_180D8CCD4`
- size: `1090`
- prototype: `__int64 __fastcall(Jot *this)`
- caller_count: `6`
- callee_count: `20`
- tags: ``

## callers

- `0x180092830`
- `0x1802a0ef0`
- `0x180c40e3c`
- `0x180cba81c`
- `0x180fd0467`
- `0x180fe89a8`

## callees

- `0x180022560`
- `0x18002e2b0`
- `0x18002f7b0`
- `0x180057078`
- `0x18023ccd0`
- `0x18029c47c`
- `0x1802c6af0`
- `0x1802d8ba0`
- `0x1802de200`
- `0x1802de3a0`
- `0x1803b2060`
- `0x18058f1f0`
- `0x180661630`
- `0x1806617f0`
- `0x180c38110`
- `0x180d8cb14`
- `0x180d8cb54`
- `0x180d8cc14`
- `0x180d8ccd4`
- `0x180eb8c78`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x180d8cf2b`
- `KERNEL32!CreateEventExW` at `0x180d8cf2b`
- `KERNEL32!CloseHandle` at `0x180d8d021`
- `KERNEL32!CloseHandle` at `0x180d8d021`
- `KERNEL32!SetLastError` at `0x180d8cd91`
- `KERNEL32!SetLastError` at `0x180d8ce67`
- `KERNEL32!SetLastError` at `0x180d8d0d8`
- `KERNEL32!SetLastError` at `0x180d8cd91`
- `KERNEL32!SetLastError` at `0x180d8ce67`
- `KERNEL32!SetLastError` at `0x180d8d0d8`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180d8cd4a`
- `MSVCP140!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180d8cd4a`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180d8cd00`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180d8cd00`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180d8cffa`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180d8cffa`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180d8cd35`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180d8cf73`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180d8cd35`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180d8cf73`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x180d8ce72`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x180d8d0e3`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x180d8ce72`
- `Mso20Win32Client!Mso20Win32Client_7228` at `0x180d8d0e3`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x180d8d10f`
- `Mso20Win32Client!Mso20Win32Client_21217` at `0x180d8d10f`
- `Mso20Win32Client!Mso20Win32Client_45473` at `0x180d8d102`
- `Mso20Win32Client!Mso20Win32Client_45473` at `0x180d8d102`

## pseudocode

```c
void __fastcall sub_180D8CCD4(Jot *this)
{
  const struct std::exception_ptr *v2; // rdx
  __int128 v3; // [rsp+50h] [rbp-B8h] BYREF
  __int128 *v4; // [rsp+60h] [rbp-A8h]
  Jot *v5; // [rsp+68h] [rbp-A0h]

  v5 = this;
  if ( __ExceptionPtrToBool(this) && !(unsigned __int8)sub_18029C47C(this, 0) )
  {
    Jot::GetErrorCode(this, v2);
    v3 = 0;
    __ExceptionPtrCopy(&v3, this);
    v4 = &v3;
    __ExceptionPtrRethrow(&v3);
  }
}

```

## disassembly

```asm
0x180d8ccd4  mov     [rsp+arg_10], rbx
0x180d8ccd9  push    r14
0x180d8ccdb  sub     rsp, 100h
0x180d8cce2  mov     rax, cs:__security_cookie
0x180d8cce9  xor     rax, rsp
0x180d8ccec  mov     [rsp+108h+var_18], rax
0x180d8ccf4  mov     rbx, rcx
0x180d8ccf7  mov     [rsp+108h+var_A0], rcx
0x180d8ccfc  mov     [rsp+108h+var_C0], edx
0x180d8cd00  call    cs:?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180d8cd06  test    al, al
0x180d8cd08  jz      short loc_180D8CD51
0x180d8cd0a  xor     edx, edx
0x180d8cd0c  mov     rcx, rbx
0x180d8cd0f  call    sub_18029C47C
0x180d8cd14  test    al, al
0x180d8cd16  jnz     short loc_180D8CD51
0x180d8cd18  mov     rcx, rbx; this
0x180d8cd1b  call    ?GetErrorCode@Jot@@YAKAEBVexception_ptr@std@@@Z; Jot::GetErrorCode(std::exception_ptr const &)
0x180d8cd20  mov     [rsp+108h+dwErrCode], eax
0x180d8cd24  xorps   xmm0, xmm0
0x180d8cd27  movdqu  [rsp+108h+var_B8], xmm0
0x180d8cd2d  mov     rdx, rbx
0x180d8cd30  lea     rcx, [rsp+108h+var_B8]
0x180d8cd35  call    cs:?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180d8cd3b  lea     rax, [rsp+108h+var_B8]
0x180d8cd40  mov     [rsp+108h+var_A8], rax
0x180d8cd45  lea     rcx, [rsp+108h+var_B8]
0x180d8cd4a  call    cs:?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180d8cd50  nop
0x180d8cd51  mov     rcx, [rsp+108h+var_18]
0x180d8cd59  xor     rcx, rsp; StackCookie
0x180d8cd5c  call    __security_check_cookie
0x180d8cd61  mov     rbx, [rsp+108h+arg_10]
0x180d8cd69  add     rsp, 100h
0x180d8cd70  pop     r14
0x180d8cd72  retn
0x180d8cd73  jmp     short loc_180D8CD51
0x180d8cd75  jmp     short loc_180D8CD51
0x180d8cd77  jmp     short loc_180D8CD51
0x180d8cd79  jmp     short loc_180D8CD51
0x180d8cd7b  jmp     short loc_180D8CD51
0x180d8cd7d  jmp     short loc_180D8CD51
0x180d8cd7f  jmp     short loc_180D8CD51
0x180d8cd81  jmp     short loc_180D8CD51
0x180d8cd83  jmp     short loc_180D8CD51
0x180d8cd85  jmp     short loc_180D8CD51
0x180d8cd87  jmp     short loc_180D8CD51
0x180d8cd89  jmp     short loc_180D8CD51
0x180d8cd8b  mov     ebx, [rsp+108h+dwErrCode]
0x180d8cd8f  mov     ecx, ebx; dwErrCode
0x180d8cd91  call    cs:SetLastError
0x180d8cd97  mov     r14, [rsp+108h+var_A0]
0x180d8cd9c  mov     rcx, r14; this
0x180d8cd9f  call    ?IsFileCorruptionError@Jot@@YA_NAEBVexception_ptr@std@@@Z; Jot::IsFileCorruptionError(std::exception_ptr const &)
0x180d8cda4  test    al, al
0x180d8cda6  jnz     loc_180D8D02C
0x180d8cdac  mov     rcx, r14
0x180d8cdaf  call    sub_180C38110
0x180d8cdb4  test    al, al
0x180d8cdb6  jnz     loc_180D8D02C
0x180d8cdbc  mov     edx, 10178h; unsigned int
0x180d8cdc1  mov     ecx, 40B7D8h; this
0x180d8cdc6  mov     r8d, 5; unsigned int
0x180d8cdcc  call    ?ShouldLogTtid@Jot@@YA_NKII@Z; Jot::ShouldLogTtid(ulong,uint,uint)
0x180d8cdd1  test    al, al
0x180d8cdd3  jz      loc_180D8CE5A
0x180d8cdd9  lea     rax, off_181510A58
0x180d8cde0  mov     [rsp+108h+var_68], rax
0x180d8cde8  lea     rax, [rsp+108h+var_50]
0x180d8cdf0  mov     [rsp+108h+var_60], rax
0x180d8cdf8  mov     [rsp+108h+var_58], 32h ; '2'
0x180d8ce03  mov     edx, ebx
0x180d8ce05  xor     r9d, r9d
0x180d8ce08  lea     r8d, [r9+0Ah]
0x180d8ce0c  lea     rcx, [rsp+108h+var_68]; int
0x180d8ce14  call    sub_18058F1F0
0x180d8ce19  lea     r8, [rsp+108h+var_68]
0x180d8ce21  lea     rcx, [rsp+108h+var_90]
0x180d8ce26  call    sub_180D8CC14
0x180d8ce2b  nop
0x180d8ce2c  cmp     qword ptr [rax+18h], 7
0x180d8ce31  jbe     short loc_180D8CE36
0x180d8ce33  mov     rax, [rax]
0x180d8ce36  mov     r9, rax; unsigned int
0x180d8ce39  mov     edx, 10178h; unsigned int
0x180d8ce3e  mov     ecx, 40B7D8h; this
0x180d8ce43  mov     r8d, 5; unsigned int
0x180d8ce49  call    ?WriteToLogCore@Jot@@YAXKIIPEB_W@Z; Jot::WriteToLogCore(ulong,uint,uint,wchar_t const *)
0x180d8ce4e  nop
0x180d8ce4f  lea     rcx, [rsp+108h+var_90]
0x180d8ce54  call    sub_1802D8BA0
0x180d8ce59  nop
0x180d8ce5a  jmp     short loc_180D8CE65
0x180d8ce5c  mov     ebx, [rsp+108h+dwErrCode]
0x180d8ce60  mov     r14, [rsp+108h+var_A0]
0x180d8ce65  mov     ecx, ebx; dwErrCode
0x180d8ce67  call    cs:SetLastError
0x180d8ce6d  mov     ecx, 3773636Ah
0x180d8ce72  call    cs:Mso20Win32Client_7228
0x180d8ce78  call    ?JotMain_IsOnMainThread@Jot@@YA_NXZ; Jot::JotMain_IsOnMainThread(void)
0x180d8ce7d  test    al, al
0x180d8ce7f  jz      loc_180D8CF15
0x180d8ce85  lea     rax, [rsp+108h+var_68]
0x180d8ce8d  mov     [rsp+108h+var_A8], rax
0x180d8ce92  mov     [rsp+108h+var_30], 0
0x180d8ce9e  mov     [rsp+108h+var_E8], 0
0x180d8cea6  xor     r9d, r9d
0x180d8cea9  xor     r8d, r8d
0x180d8ceac  lea     edx, [r9+1]
0x180d8ceb0  lea     rcx, [rsp+108h+var_A0]
0x180d8ceb5  call    ??0CDialogButtonSet@Jot@@QEAA@W4DisplayErrorResponse@1@000@Z; Jot::CDialogButtonSet::CDialogButtonSet(Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse)
0x180d8ceba  movups  xmm0, xmmword ptr [rax]
0x180d8cebd  movdqu  [rsp+108h+var_B8], xmm0
0x180d8cec3  lea     rax, [rsp+108h+var_68]
0x180d8cecb  mov     [rsp+108h+var_D8], rax; __int64
0x180d8ced0  mov     [rsp+108h+var_E0], 1; char
0x180d8ced5  mov     [rsp+108h+var_E8], 0Eh; int
0x180d8cedd  mov     r9b, 1
0x180d8cee0  lea     r8, [rsp+108h+var_B8]
0x180d8cee5  mov     edx, [rsp+108h+var_C0]
0x180d8cee9  mov     rcx, r14; this
0x180d8ceec  call    ?DisplayErrorDialogForError@Jot@@YA?AW4DisplayErrorResponse@1@AEBVexception_ptr@std@@W4DisplayErrorContext@1@VCDialogButtonSet@1@_N13V?$function@$$A6AXXZ@4@@Z; Jot::DisplayErrorDialogForError(std::exception_ptr const &,Jot::DisplayErrorContext,Jot::CDialogButtonSet,bool,Jot::DisplayErrorContext,bool,std::function<void (void)>)
0x180d8cef1  mov     rcx, cs:qword_1815304B0
0x180d8cef8  mov     rax, [rcx]
0x180d8cefb  mov     rax, [rax+0F0h]
0x180d8cf02  call    cs:__guard_dispatch_icall_fptr
0x180d8cf08  mov     rcx, r14; this
0x180d8cf0b  call    sub_180EB8C78
0x180d8cf10  jmp     loc_180D8CD51
0x180d8cf15  mov     qword ptr [rsp+108h+dwErrCode], 0
0x180d8cf1e  mov     r9d, 100002h; dwDesiredAccess
0x180d8cf24  xor     r8d, r8d; dwFlags
0x180d8cf27  xor     edx, edx; lpName
0x180d8cf29  xor     ecx, ecx; lpEventAttributes
0x180d8cf2b  call    cs:CreateEventExW
0x180d8cf31  cmp     qword ptr [rsp+108h+dwErrCode], rax
0x180d8cf36  jz      short loc_180D8CF45
0x180d8cf38  mov     rdx, rax
0x180d8cf3b  lea     rcx, [rsp+108h+dwErrCode]
0x180d8cf40  call    sub_18002E2B0
0x180d8cf45  lea     rax, [rsp+108h+var_68]
0x180d8cf4d  mov     [rsp+108h+var_A8], rax
0x180d8cf52  lea     rax, [rsp+108h+dwErrCode]
0x180d8cf57  mov     [rsp+108h+var_90], rax
0x180d8cf5c  xorps   xmm0, xmm0
0x180d8cf5f  movdqu  [rsp+108h+var_88], xmm0
0x180d8cf68  mov     rdx, r14
0x180d8cf6b  lea     rcx, [rsp+108h+var_88]
0x180d8cf73  call    cs:?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180d8cf79  mov     [rsp+108h+var_30], 0
0x180d8cf85  lea     rdx, [rsp+108h+var_90]
0x180d8cf8a  lea     rcx, [rsp+108h+var_68]
0x180d8cf92  call    sub_180D8CB14
0x180d8cf97  mov     [rsp+108h+var_30], rax
0x180d8cf9f  mov     [rsp+108h+var_E8], 0
0x180d8cfa7  xor     r9d, r9d
0x180d8cfaa  xor     r8d, r8d
0x180d8cfad  lea     edx, [r9+1]
0x180d8cfb1  lea     rcx, [rsp+108h+var_A0]
0x180d8cfb6  call    ??0CDialogButtonSet@Jot@@QEAA@W4DisplayErrorResponse@1@000@Z; Jot::CDialogButtonSet::CDialogButtonSet(Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse)
0x180d8cfbb  movups  xmm0, xmmword ptr [rax]
0x180d8cfbe  movdqu  [rsp+108h+var_B8], xmm0
0x180d8cfc4  lea     rax, [rsp+108h+var_68]
0x180d8cfcc  mov     [rsp+108h+var_D8], rax; __int64
0x180d8cfd1  mov     [rsp+108h+var_E0], 1; char
0x180d8cfd6  mov     [rsp+108h+var_E8], 0Eh; int
0x180d8cfde  xor     r9d, r9d
0x180d8cfe1  lea     r8, [rsp+108h+var_B8]
0x180d8cfe6  mov     edx, [rsp+108h+var_C0]
0x180d8cfea  mov     rcx, r14; this
0x180d8cfed  call    ?DisplayErrorDialogForError@Jot@@YA?AW4DisplayErrorResponse@1@AEBVexception_ptr@std@@W4DisplayErrorContext@1@VCDialogButtonSet@1@_N13V?$function@$$A6AXXZ@4@@Z; Jot::DisplayErrorDialogForError(std::exception_ptr const &,Jot::DisplayErrorContext,Jot::CDialogButtonSet,bool,Jot::DisplayErrorContext,bool,std::function<void (void)>)
0x180d8cff2  lea     rcx, [rsp+108h+var_88]
0x180d8cffa  call    cs:?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180d8d000  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180d8d004  mov     rcx, qword ptr [rsp+108h+dwErrCode]; hHandle
0x180d8d009  call    sub_180057078
0x180d8d00e  mov     rcx, qword ptr [rsp+108h+dwErrCode]; hObject
0x180d8d013  lea     rax, [rcx-1]
0x180d8d017  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180d8d01b  ja      loc_180D8CD51
0x180d8d021  call    cs:__imp_CloseHandle
0x180d8d027  jmp     loc_180D8CD51
0x180d8d02c  mov     edx, 10178h; unsigned int
0x180d8d031  mov     r8d, 5; unsigned int
0x180d8d037  mov     r14d, 40B7D7h
0x180d8d03d  mov     ecx, r14d; this
0x180d8d040  call    ?ShouldLogTtid@Jot@@YA_NKII@Z; Jot::ShouldLogTtid(ulong,uint,uint)
0x180d8d045  test    al, al
0x180d8d047  jz      loc_180D8D0D0
0x180d8d04d  lea     rax, off_181510A58
0x180d8d054  mov     [rsp+108h+var_68], rax
0x180d8d05c  lea     rax, [rsp+108h+var_50]
0x180d8d064  mov     [rsp+108h+var_60], rax
0x180d8d06c  mov     [rsp+108h+var_58], 32h ; '2'
0x180d8d077  mov     rdx, rbx
0x180d8d07a  xor     r9d, r9d
0x180d8d07d  lea     r8d, [r9+0Ah]
0x180d8d081  lea     rcx, [rsp+108h+var_68]; int
0x180d8d089  call    sub_18058F1F0
0x180d8d08e  lea     r8, [rsp+108h+var_68]
0x180d8d096  lea     rcx, [rsp+108h+var_90]
0x180d8d09b  call    sub_180D8CB54
0x180d8d0a0  nop
0x180d8d0a1  cmp     qword ptr [rax+18h], 7
0x180d8d0a6  jbe     short loc_180D8D0AB
0x180d8d0a8  mov     rax, [rax]
0x180d8d0ab  mov     r9, rax; unsigned int
0x180d8d0ae  mov     edx, 10178h; unsigned int
0x180d8d0b3  mov     r8d, 5; unsigned int
0x180d8d0b9  mov     ecx, r14d; this
0x180d8d0bc  call    ?WriteToLogCore@Jot@@YAXKIIPEB_W@Z; Jot::WriteToLogCore(ulong,uint,uint,wchar_t const *)
0x180d8d0c1  nop
0x180d8d0c2  lea     rcx, [rsp+108h+var_90]
0x180d8d0c7  call    sub_1802D8BA0
0x180d8d0cc  nop
0x180d8d0cd  nop     dword ptr [rax]
0x180d8d0d0  jmp     short loc_180D8D0D6
0x180d8d0d2  mov     ebx, [rsp+108h+dwErrCode]
0x180d8d0d6  mov     ecx, ebx; dwErrCode
0x180d8d0d8  call    cs:SetLastError
0x180d8d0de  mov     ecx, 37736368h
0x180d8d0e3  call    cs:Mso20Win32Client_7228
0x180d8d0e9  mov     rcx, cs:qword_1815304B0
0x180d8d0f0  mov     rax, [rcx]
0x180d8d0f3  mov     rax, [rax+0F0h]
0x180d8d0fa  call    cs:__guard_dispatch_icall_fptr
0x180d8d100  xor     ecx, ecx
0x180d8d102  call    cs:Mso20Win32Client_45473
0x180d8d108  xor     edx, edx
0x180d8d10a  mov     ecx, 2360131Dh
0x180d8d10f  call    cs:Mso20Win32Client_21217
```
