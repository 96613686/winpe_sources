# CSystemMSIController::Initialize(_IMAGELIST *)

- ea: `0x180032730`
- end: `0x1800327e1`
- name: `?Initialize@CSystemMSIController@@UEAAJPEAU_IMAGELIST@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CSystemMSIController *__hidden this, struct _IMAGELIST *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180032730`
- `0x18003ea60`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18003277d`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18003277d`
- `osbaseln!OpenOsBaseline` at `0x180032790`
- `osbaseln!OpenOsBaseline` at `0x180032790`
- `osbaseln!CloseOsBaseline` at `0x1800327b1`
- `osbaseln!CloseOsBaseline` at `0x1800327b1`

## pseudocode

```c
__int64 __fastcall CSystemMSIController::Initialize(CSystemMSIController *this, struct _IMAGELIST *a2)
{
  unsigned int v4; // ebx
  void *v6; // [rsp+20h] [rbp-148h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-138h] BYREF
  unsigned __int16 v8; // [rsp+144h] [rbp-24h]

  v6 = 0;
  VersionInformation.dwOSVersionInfoSize = 284;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  GetVersionExW(&VersionInformation);
  if ( (unsigned int)OpenOsBaseline(v8, &v6) )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    v4 = CSystemMSIController::_EnumerateSystemMsi(this, a2, v6);
    CloseOsBaseline(v6);
  }
  return v4;
}

```

## disassembly

```asm
0x180032730  mov     [rsp+arg_10], rbx
0x180032735  push    rdi
0x180032736  sub     rsp, 160h
0x18003273d  mov     rax, cs:__security_cookie
0x180032744  xor     rax, rsp
0x180032747  mov     [rsp+168h+var_18], rax
0x18003274f  mov     rdi, rdx
0x180032752  mov     [rsp+168h+var_148], 0
0x18003275b  mov     rbx, rcx
0x18003275e  mov     [rsp+168h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180032766  xor     edx, edx; Val
0x180032768  lea     rcx, [rsp+168h+VersionInformation.dwMajorVersion]; void *
0x18003276d  mov     r8d, 118h; Size
0x180032773  call    memset_0
0x180032778  lea     rcx, [rsp+168h+VersionInformation]; lpVersionInformation
0x18003277d  call    cs:__imp_GetVersionExW
0x180032783  movzx   ecx, [rsp+168h+var_24]
0x18003278b  lea     rdx, [rsp+168h+var_148]
0x180032790  call    cs:__imp_OpenOsBaseline
0x180032796  test    eax, eax
0x180032798  jnz     short loc_1800327B9
0x18003279a  mov     r8, [rsp+168h+var_148]; void *
0x18003279f  mov     rdx, rdi; struct _IMAGELIST *
0x1800327a2  mov     rcx, rbx; this
0x1800327a5  call    ?_EnumerateSystemMsi@CSystemMSIController@@AEAAJPEAU_IMAGELIST@@PEAX@Z; CSystemMSIController::_EnumerateSystemMsi(_IMAGELIST *,void *)
0x1800327aa  mov     rcx, [rsp+168h+var_148]
0x1800327af  mov     ebx, eax
0x1800327b1  call    cs:__imp_CloseOsBaseline
0x1800327b7  jmp     short loc_1800327BE
0x1800327b9  mov     ebx, 80004005h
0x1800327be  mov     eax, ebx
0x1800327c0  mov     rcx, [rsp+168h+var_18]
0x1800327c8  xor     rcx, rsp; StackCookie
0x1800327cb  call    __security_check_cookie
0x1800327d0  mov     rbx, [rsp+168h+arg_10]
0x1800327d8  add     rsp, 160h
0x1800327df  pop     rdi
0x1800327e0  retn
```
