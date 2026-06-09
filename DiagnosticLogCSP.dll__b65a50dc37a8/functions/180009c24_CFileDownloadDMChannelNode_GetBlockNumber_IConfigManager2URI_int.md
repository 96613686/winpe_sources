# CFileDownloadDMChannelNode::GetBlockNumber(IConfigManager2URI *,int &)

- ea: `0x180009c24`
- end: `0x180009c99`
- name: `?GetBlockNumber@CFileDownloadDMChannelNode@@KAJPEAUIConfigManager2URI@@AEAH@Z`
- size: `117`
- prototype: `__int64 __fastcall(struct IConfigManager2URI *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800099a0`
- `0x18000a320`

## callees

- `0x180002e40`
- `0x180009c24`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall CFileDownloadDMChannelNode::GetBlockNumber(struct IConfigManager2URI *a1, int *a2)
{
  int v3; // ebx
  int v4; // eax
  unsigned int v5; // ecx
  wchar_t *Buffer; // [rsp+30h] [rbp+8h] BYREF

  Buffer = 0;
  *a2 = 0;
  if ( a1 )
  {
    v3 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, wchar_t **))(*(_QWORD *)a1 + 88LL))(
           a1,
           5,
           &Buffer);
    if ( v3 >= 0 )
    {
      v4 = swscanf_s(Buffer, L"%d", a2);
      v5 = v3;
      if ( v4 != 1 )
        return (unsigned int)-2147024809;
      return v5;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009c24  mov     [rsp+arg_8], rbx
0x180009c29  push    rdi
0x180009c2a  sub     rsp, 20h
0x180009c2e  mov     [rsp+28h+Buffer], 0
0x180009c37  mov     rdi, rdx
0x180009c3a  mov     dword ptr [rdx], 0
0x180009c40  test    rcx, rcx
0x180009c43  jnz     short loc_180009C4C
0x180009c45  mov     ebx, 80070057h
0x180009c4a  jmp     short loc_180009C8B
0x180009c4c  mov     rax, [rcx]
0x180009c4f  lea     r8, [rsp+28h+Buffer]
0x180009c54  mov     edx, 5
0x180009c59  mov     rax, [rax+58h]
0x180009c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c62  mov     ebx, eax
0x180009c64  test    eax, eax
0x180009c66  js      short loc_180009C8B
0x180009c68  mov     rcx, [rsp+28h+Buffer]; Buffer
0x180009c6d  lea     rdx, aD; "%d"
0x180009c74  mov     r8, rdi
0x180009c77  call    swscanf_s
0x180009c7c  mov     ecx, ebx
0x180009c7e  cmp     eax, 1
0x180009c81  mov     ebx, 80070057h
0x180009c86  cmovnz  ecx, ebx
0x180009c89  mov     ebx, ecx
0x180009c8b  mov     eax, ebx
0x180009c8d  mov     rbx, [rsp+28h+arg_8]
0x180009c92  add     rsp, 20h
0x180009c96  pop     rdi
0x180009c97  retn
```
