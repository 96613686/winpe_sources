# CallerIdentity::GetPackageSidFromProcessHandle(void *,void * *)

- ea: `0x14001dd70`
- end: `0x14001dde4`
- name: `?GetPackageSidFromProcessHandle@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(CallerIdentity *this, _QWORD *, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140018cf8`
- `0x14001d8dc`
- `0x14001dcfc`

## callees

- `0x14001d6c0`
- `0x14001dd70`
- `0x14001ddec`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14001ddd1`
- `KERNEL32!CloseHandle` at `0x14001ddd1`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromProcessHandle(CallerIdentity *this, _QWORD *a2, void **a3)
{
  int v4; // eax
  void **v5; // r8
  signed int PackageSidFromProcessToken; // ebx
  char *v7; // rcx
  HANDLE hObject; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  hObject = 0;
  v4 = ARI::ProcessToken::SysAppId::OpenTokenForProcess(this, &hObject, a3);
  PackageSidFromProcessToken = v4;
  if ( v4 > 0 )
    PackageSidFromProcessToken = (unsigned __int16)v4 | 0x80070000;
  if ( PackageSidFromProcessToken >= 0 )
    PackageSidFromProcessToken = CallerIdentity::GetPackageSidFromProcessToken(hObject, a2, v5);
  v7 = (char *)hObject;
  hObject = 0;
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v7);
  return (unsigned int)PackageSidFromProcessToken;
}

```

## disassembly

```asm
0x14001dd70  mov     [rsp+arg_0], rbx
0x14001dd75  push    rdi
0x14001dd76  sub     rsp, 20h
0x14001dd7a  mov     rdi, rdx
0x14001dd7d  mov     qword ptr [rdx], 0
0x14001dd84  lea     rdx, [rsp+28h+hObject]; TokenHandle
0x14001dd89  mov     [rsp+28h+hObject], 0
0x14001dd92  call    ?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z; ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)
0x14001dd97  mov     ebx, eax
0x14001dd99  test    eax, eax
0x14001dd9b  jle     short loc_14001DDA6
0x14001dd9d  movzx   ebx, ax
0x14001dda0  or      ebx, 80070000h
0x14001dda6  test    ebx, ebx
0x14001dda8  js      short loc_14001DDB9
0x14001ddaa  mov     rcx, [rsp+28h+hObject]; TokenHandle
0x14001ddaf  mov     rdx, rdi; void *
0x14001ddb2  call    ?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z; CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)
0x14001ddb7  mov     ebx, eax
0x14001ddb9  mov     rcx, [rsp+28h+hObject]; hObject
0x14001ddbe  mov     [rsp+28h+hObject], 0
0x14001ddc7  lea     rax, [rcx-1]
0x14001ddcb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ddcf  ja      short loc_14001DDD7
0x14001ddd1  call    cs:__imp_CloseHandle
0x14001ddd7  mov     eax, ebx
0x14001ddd9  mov     rbx, [rsp+28h+arg_0]
0x14001ddde  add     rsp, 20h
0x14001dde2  pop     rdi
0x14001dde3  retn
```
