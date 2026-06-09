# FreeSortedStorageElements(HINSTANCE__ *,tagSTATSTG *,ulong)

- ea: `0x180004ad0`
- end: `0x180004b56`
- name: `?FreeSortedStorageElements@@YAXPEAUHINSTANCE__@@PEAUtagSTATSTG@@K@Z`
- size: `134`
- prototype: `void __fastcall(HINSTANCE, struct tagSTATSTG *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003370`
- `0x180003a70`

## callees

- `0x180004ad0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180004aff`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180004aff`

## string_xrefs

- `0x180004af3`: `CoTaskMemFree`

## pseudocode

```c
void __fastcall FreeSortedStorageElements(HINSTANCE a1, struct tagSTATSTG *a2, unsigned int a3)
{
  void (*ProcAddress)(void); // rbp
  unsigned int i; // ebx

  if ( a2 )
  {
    if ( a3 )
    {
      if ( a1 )
      {
        ProcAddress = (void (*)(void))GetProcAddress(a1, "CoTaskMemFree");
        if ( ProcAddress )
        {
          for ( i = 0; i < a3; ++i )
          {
            if ( *((_QWORD *)a2 + 10 * (int)i) )
              ProcAddress();
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180004ad0  test    rdx, rdx
0x180004ad3  jz      locret_180004B55
0x180004ad9  mov     [rsp+arg_10], rsi
0x180004ade  push    rdi
0x180004adf  sub     rsp, 20h
0x180004ae3  mov     edi, r8d
0x180004ae6  mov     rsi, rdx
0x180004ae9  test    r8d, r8d
0x180004aec  jz      short loc_180004B4B
0x180004aee  test    rcx, rcx
0x180004af1  jz      short loc_180004B4B
0x180004af3  lea     rdx, aCotaskmemfree; "CoTaskMemFree"
0x180004afa  mov     [rsp+28h+arg_8], rbp
0x180004aff  call    cs:__imp_GetProcAddress
0x180004b05  mov     rbp, rax
0x180004b08  test    rax, rax
0x180004b0b  jz      short loc_180004B46
0x180004b0d  mov     [rsp+28h+arg_0], rbx
0x180004b12  xor     ebx, ebx
0x180004b14  test    edi, edi
0x180004b16  jz      short loc_180004B41
0x180004b18  nop     dword ptr [rax+rax+00000000h]
0x180004b20  movsxd  rcx, ebx
0x180004b23  lea     rdx, [rcx+rcx*4]
0x180004b27  add     rdx, rdx
0x180004b2a  mov     rcx, [rsi+rdx*8]
0x180004b2e  test    rcx, rcx
0x180004b31  jz      short loc_180004B3B
0x180004b33  mov     rax, rbp
0x180004b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b3b  inc     ebx
0x180004b3d  cmp     ebx, edi
0x180004b3f  jb      short loc_180004B20
0x180004b41  mov     rbx, [rsp+28h+arg_0]
0x180004b46  mov     rbp, [rsp+28h+arg_8]
0x180004b4b  mov     rsi, [rsp+28h+arg_10]
0x180004b50  add     rsp, 20h
0x180004b54  pop     rdi
0x180004b55  retn
```
