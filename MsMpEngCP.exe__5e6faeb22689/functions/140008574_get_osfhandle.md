# _get_osfhandle

- ea: `0x140008574`
- end: `0x1400085e9`
- name: `_get_osfhandle`
- size: `117`
- prototype: `intptr_t __cdecl(int FileHandle)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000b55c`
- `0x14000c568`
- `0x14000ca98`

## callees

- `0x140006544`
- `0x140006878`
- `0x14000689c`
- `0x140008574`

## pseudocode

```c
intptr_t __cdecl get_osfhandle(int FileHandle)
{
  unsigned __int64 v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rax

  if ( FileHandle == -2 )
  {
    *(_DWORD *)sub_140006878() = 0;
    *(_DWORD *)sub_14000689C() = 9;
  }
  else
  {
    if ( FileHandle >= 0 && FileHandle < (unsigned int)dword_14001AB50 )
    {
      v1 = FileHandle;
      v2 = FileHandle & 0x3F;
      v3 = qword_14001A750[v1 >> 6];
      if ( (*(_BYTE *)(v3 + 72 * v2 + 56) & 1) != 0 )
        return *(_QWORD *)(v3 + 72 * v2 + 40);
    }
    *(_DWORD *)sub_140006878() = 0;
    *(_DWORD *)sub_14000689C() = 9;
    invalid_parameter_noinfo();
  }
  return -1;
}

```

## disassembly

```asm
0x140008574  sub     rsp, 28h
0x140008578  cmp     ecx, 0FFFFFFFEh
0x14000857b  jnz     short loc_140008592
0x14000857d  call    sub_140006878
0x140008582  and     dword ptr [rax], 0
0x140008585  call    sub_14000689C
0x14000858a  mov     dword ptr [rax], 9
0x140008590  jmp     short loc_1400085E0
0x140008592  test    ecx, ecx
0x140008594  js      short loc_1400085C8
0x140008596  cmp     ecx, cs:dword_14001AB50
0x14000859c  jnb     short loc_1400085C8
0x14000859e  movsxd  rcx, ecx
0x1400085a1  lea     r8, qword_14001A750
0x1400085a8  mov     rax, rcx
0x1400085ab  and     ecx, 3Fh
0x1400085ae  shr     rax, 6
0x1400085b2  lea     rdx, [rcx+rcx*8]
0x1400085b6  mov     rax, [r8+rax*8]
0x1400085ba  test    byte ptr [rax+rdx*8+38h], 1
0x1400085bf  jz      short loc_1400085C8
0x1400085c1  mov     rax, [rax+rdx*8+28h]
0x1400085c6  jmp     short loc_1400085E4
0x1400085c8  call    sub_140006878
0x1400085cd  and     dword ptr [rax], 0
0x1400085d0  call    sub_14000689C
0x1400085d5  mov     dword ptr [rax], 9
0x1400085db  call    _invalid_parameter_noinfo
0x1400085e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400085e4  add     rsp, 28h
0x1400085e8  retn
```
