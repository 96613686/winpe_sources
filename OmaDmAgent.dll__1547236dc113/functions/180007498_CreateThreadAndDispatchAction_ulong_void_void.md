# CreateThreadAndDispatchAction(ulong (*)(void *),void *)

- ea: `0x180007498`
- end: `0x1800075a7`
- name: `?CreateThreadAndDispatchAction@@YAJP6AKPEAX@Z0@Z`
- size: `271`
- prototype: `__int64 __fastcall(LPTHREAD_START_ROUTINE lpStartAddress, void *lpParameter)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180019f78`
- `0x18001a2c8`

## callees

- `0x180007498`
- `0x18000a290`
- `0x18000a2c0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000751e`
- `KERNEL32!CloseHandle` at `0x18000751e`
- `KERNEL32!GetLastError` at `0x18000756e`
- `KERNEL32!GetLastError` at `0x18000756e`
- `KERNEL32!WaitForSingleObject` at `0x1800074dd`
- `KERNEL32!WaitForSingleObject` at `0x1800074dd`
- `KERNEL32!CreateThread` at `0x1800074bd`
- `KERNEL32!CreateThread` at `0x1800074bd`

## pseudocode

```c
__int64 __fastcall CreateThreadAndDispatchAction(LPTHREAD_START_ROUTINE lpStartAddress, void *lpParameter)
{
  HANDLE Thread; // rax
  void *v3; // rdi
  DWORD LastError; // eax

  Thread = CreateThread(0, 0, lpStartAddress, lpParameter, 0, 0);
  v3 = Thread;
  if ( Thread )
  {
    if ( WaitForSingleObject(Thread, 0x493E0u)
      && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids);
    }
    if ( !CloseHandle(v3) && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids);
  }
  else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x180007498  mov     [rsp+arg_0], rbx
0x18000749d  push    rdi
0x18000749e  sub     rsp, 30h
0x1800074a2  mov     r9, rdx; lpParameter
0x1800074a5  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800074ae  mov     r8, rcx; lpStartAddress
0x1800074b1  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800074b9  xor     edx, edx; dwStackSize
0x1800074bb  xor     ecx, ecx; lpThreadAttributes
0x1800074bd  call    cs:__imp_CreateThread
0x1800074c4  nop     dword ptr [rax+rax+00h]
0x1800074c9  mov     rdi, rax
0x1800074cc  test    rax, rax
0x1800074cf  jz      loc_180007555
0x1800074d5  mov     edx, 493E0h; dwMilliseconds
0x1800074da  mov     rcx, rax; hHandle
0x1800074dd  call    cs:__imp_WaitForSingleObject
0x1800074e4  nop     dword ptr [rax+rax+00h]
0x1800074e9  lea     rbx, WPP_GLOBAL_Control
0x1800074f0  test    eax, eax
0x1800074f2  jz      short loc_18000751B
0x1800074f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074fb  cmp     rcx, rbx
0x1800074fe  jz      short loc_18000751B
0x180007500  test    byte ptr [rcx+1Ch], 4
0x180007504  jz      short loc_18000751B
0x180007506  mov     rcx, [rcx+10h]
0x18000750a  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180007511  mov     edx, 68h ; 'h'
0x180007516  call    WPP_SF_
0x18000751b  mov     rcx, rdi; hObject
0x18000751e  call    cs:__imp_CloseHandle
0x180007525  nop     dword ptr [rax+rax+00h]
0x18000752a  test    eax, eax
0x18000752c  jnz     short loc_180007599
0x18000752e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007535  cmp     rcx, rbx
0x180007538  jz      short loc_180007599
0x18000753a  test    byte ptr [rcx+1Ch], 4
0x18000753e  jz      short loc_180007599
0x180007540  mov     rcx, [rcx+10h]
0x180007544  lea     edx, [rax+69h]
0x180007547  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x18000754e  call    WPP_SF_
0x180007553  jmp     short loc_180007599
0x180007555  mov     rax, cs:WPP_GLOBAL_Control
0x18000755c  lea     rbx, WPP_GLOBAL_Control
0x180007563  cmp     rax, rbx
0x180007566  jz      short loc_180007599
0x180007568  test    byte ptr [rax+1Ch], 4
0x18000756c  jz      short loc_180007599
0x18000756e  call    cs:__imp_GetLastError
0x180007575  nop     dword ptr [rax+rax+00h]
0x18000757a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007581  lea     r8, WPP_74f8d64cc84e33ec48a9ebb7f3db7a85_Traceguids
0x180007588  mov     edx, 6Ah ; 'j'
0x18000758d  mov     r9d, eax
0x180007590  mov     rcx, [rcx+10h]
0x180007594  call    WPP_SF_d
0x180007599  mov     rbx, [rsp+38h+arg_0]
0x18000759e  xor     eax, eax
0x1800075a0  add     rsp, 30h
0x1800075a4  pop     rdi
0x1800075a5  retn
```
