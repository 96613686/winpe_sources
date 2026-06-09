# std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry,std::allocator<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::~vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry,std::allocator<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>(void)

- ea: `0x18001f2b4`
- end: `0x18001f337`
- name: `??1?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@QEAA@XZ`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x18001f40c`

## callees

- `0x180003914`
- `0x18001f2b4`

## pseudocode

```c
void __fastcall std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::~vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>(
        char **a1)
{
  char *v1; // rdx
  char *v3; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( (unsigned __int64)(8 * ((a1[2] - v1) >> 3)) < 0x1000 )
    {
      v3 = *a1;
    }
    else
    {
      v3 = (char *)*((_QWORD *)v1 - 1);
      if ( (unsigned __int64)(v1 - v3 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v3);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18001f2b4  push    rbx
0x18001f2b6  sub     rsp, 20h
0x18001f2ba  mov     rdx, [rcx]
0x18001f2bd  mov     rbx, rcx
0x18001f2c0  test    rdx, rdx
0x18001f2c3  jz      short loc_18001F331
0x18001f2c5  mov     rax, [rcx+10h]
0x18001f2c9  mov     rcx, 8F5C28F5C28F5C29h
0x18001f2d3  sub     rax, rdx
0x18001f2d6  sar     rax, 3
0x18001f2da  imul    rax, rcx
0x18001f2de  imul    rcx, rax, 0C8h
0x18001f2e5  cmp     rcx, 1000h
0x18001f2ec  jb      short loc_18001F30C
0x18001f2ee  mov     rax, [rdx-8]
0x18001f2f2  sub     rdx, rax
0x18001f2f5  sub     rdx, 8
0x18001f2f9  cmp     rdx, 1Fh
0x18001f2fd  ja      short loc_18001F305
0x18001f2ff  add     rcx, 27h ; '''
0x18001f303  jmp     short loc_18001F30F
0x18001f305  mov     ecx, 5
0x18001f30a  int     29h; Win8: RtlFailFast(ecx)
0x18001f30c  mov     rax, rdx
0x18001f30f  mov     rdx, rcx
0x18001f312  mov     rcx, rax; Block
0x18001f315  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f31a  mov     qword ptr [rbx], 0
0x18001f321  mov     qword ptr [rbx+8], 0
0x18001f329  mov     qword ptr [rbx+10h], 0
0x18001f331  add     rsp, 20h
0x18001f335  pop     rbx
0x18001f336  retn
```
