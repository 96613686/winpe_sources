# CBdeCfgLibraryLoader::InitializeAndHoldLibrary_Thread(void)

- ea: `0x18000d930`
- end: `0x18000d98d`
- name: `?InitializeAndHoldLibrary_Thread@CBdeCfgLibraryLoader@@AEAAJXZ`
- size: `93`
- prototype: `__int64 __fastcall(CBdeCfgLibraryLoader *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d8a0`

## callees

- `0x1800047d0`
- `0x180004ff0`
- `0x18000d930`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000d967`
- `KERNEL32!SetEvent` at `0x18000d967`
- `KERNEL32!WaitForSingleObject` at `0x18000d974`
- `KERNEL32!WaitForSingleObject` at `0x18000d974`

## pseudocode

```c
__int64 __fastcall CBdeCfgLibraryLoader::InitializeAndHoldLibrary_Thread(CBdeCfgLibraryLoader *this)
{
  unsigned int v2; // ebx
  int v3; // eax

  if ( *((_QWORD *)this + 5) )
  {
    v3 = BdeCfgInitialize();
    v2 = v3;
    if ( v3 >= 0 )
    {
      *((_DWORD *)this + 14) = v3;
      SetEvent(*((HANDLE *)this + 6));
      WaitForSingleObject(*((HANDLE *)this + 5), 0xFFFFFFFF);
    }
  }
  else
  {
    v2 = -1063256037;
  }
  BdeCfgUninitialize();
  return v2;
}

```

## disassembly

```asm
0x18000d930  mov     [rsp+arg_0], rbx
0x18000d935  push    rdi
0x18000d936  sub     rsp, 30h
0x18000d93a  mov     rdi, rcx
0x18000d93d  mov     rax, [rcx+28h]
0x18000d941  test    rax, rax
0x18000d944  jnz     short loc_18000D951
0x18000d946  mov     ebx, 0C0A0001Bh
0x18000d94b  mov     [rsp+38h+var_18], ebx
0x18000d94f  jmp     short loc_18000D97B
0x18000d951  call    ?BdeCfgInitialize@@YAJXZ; BdeCfgInitialize(void)
0x18000d956  mov     ebx, eax
0x18000d958  mov     [rsp+38h+var_18], eax
0x18000d95c  test    eax, eax
0x18000d95e  js      short loc_18000D97B
0x18000d960  mov     [rdi+38h], eax
0x18000d963  mov     rcx, [rdi+30h]; hEvent
0x18000d967  call    cs:__imp_SetEvent
0x18000d96d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d970  mov     rcx, [rdi+28h]; hHandle
0x18000d974  call    cs:__imp_WaitForSingleObject
0x18000d97a  nop
0x18000d97b  call    ?BdeCfgUninitialize@@YAJXZ; BdeCfgUninitialize(void)
0x18000d980  mov     eax, ebx
0x18000d982  mov     rbx, [rsp+38h+arg_0]
0x18000d987  add     rsp, 30h
0x18000d98b  pop     rdi
0x18000d98c  retn
0x18001428d  push    rbp
0x18001428f  sub     rsp, 20h
0x180014293  mov     rbp, rdx
0x180014296  add     rsp, 20h
0x18001429a  pop     rbp
0x18001429b  jmp     ?BdeCfgUninitialize@@YAJXZ; BdeCfgUninitialize(void)
```
