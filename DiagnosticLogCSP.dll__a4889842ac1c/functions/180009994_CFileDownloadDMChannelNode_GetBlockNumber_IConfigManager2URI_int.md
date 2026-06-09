# CFileDownloadDMChannelNode::GetBlockNumber(IConfigManager2URI *,int &)

- ea: `0x180009994`
- end: `0x180009a08`
- name: `?GetBlockNumber@CFileDownloadDMChannelNode@@KAJPEAUIConfigManager2URI@@AEAH@Z`
- size: `116`
- prototype: `__int64 __fastcall(struct IConfigManager2URI *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009710`
- `0x18000a010`

## callees

- `0x180002e10`
- `0x180009994`
- `0x180037010`

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
0x180009994  mov     [rsp+arg_8], rbx
0x180009999  push    rdi
0x18000999a  sub     rsp, 20h
0x18000999e  mov     [rsp+28h+Buffer], 0
0x1800099a7  mov     rdi, rdx
0x1800099aa  mov     dword ptr [rdx], 0
0x1800099b0  test    rcx, rcx
0x1800099b3  jnz     short loc_1800099BC
0x1800099b5  mov     ebx, 80070057h
0x1800099ba  jmp     short loc_1800099FB
0x1800099bc  mov     rax, [rcx]
0x1800099bf  lea     r8, [rsp+28h+Buffer]
0x1800099c4  mov     edx, 5
0x1800099c9  mov     rax, [rax+58h]
0x1800099cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099d2  mov     ebx, eax
0x1800099d4  test    eax, eax
0x1800099d6  js      short loc_1800099FB
0x1800099d8  mov     rcx, [rsp+28h+Buffer]; Buffer
0x1800099dd  lea     rdx, aD; "%d"
0x1800099e4  mov     r8, rdi
0x1800099e7  call    swscanf_s
0x1800099ec  mov     ecx, ebx
0x1800099ee  cmp     eax, 1
0x1800099f1  mov     ebx, 80070057h
0x1800099f6  cmovnz  ecx, ebx
0x1800099f9  mov     ebx, ecx
0x1800099fb  mov     eax, ebx
0x1800099fd  mov     rbx, [rsp+28h+arg_8]
0x180009a02  add     rsp, 20h
0x180009a06  pop     rdi
0x180009a07  retn
```
