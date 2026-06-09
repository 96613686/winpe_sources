# CreateResourceManagerProxy

- ea: `0x180013314`
- end: `0x1800133a6`
- name: `CreateResourceManagerProxy`
- size: `146`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000db70`
- `0x18000e8a0`

## callees

- `0x180002f50`
- `0x180013314`
- `0x1800148c0`
- `0x18001c010`

## pseudocode

```c
__int64 CreateResourceManagerProxy()
{
  void *v0; // rax
  int v1; // eax
  int v2; // ebx
  void (__fastcall ***v3)(_QWORD, __int64); // rcx

  v0 = operator new(0x10u);
  if ( v0 )
  {
    *((_QWORD *)v0 + 1) = 0;
    *(_QWORD *)v0 = &ResourceManagerProxy::`vftable';
    qword_18002ED78 = (__int64)v0;
    v1 = CempRpcBindToServer(qword_18001D170, (RPC_BINDING_HANDLE *)v0 + 1) | 0x10000000;
    v2 = 0;
    if ( v1 < 0 )
      v2 = v1;
    if ( v2 >= 0 )
      return 0;
    v3 = (void (__fastcall ***)(_QWORD, __int64))qword_18002ED78;
  }
  else
  {
    v3 = 0;
    v2 = -2147024882;
    qword_18002ED78 = 0;
  }
  if ( v3 )
  {
    (**v3)(v3, 1);
    qword_18002ED78 = 0;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180013314  push    rbx
0x180013316  sub     rsp, 20h
0x18001331a  mov     ecx, 10h; Size
0x18001331f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013324  test    rax, rax
0x180013327  jz      short loc_180013370
0x180013329  lea     rcx, ??_7ResourceManagerProxy@@6B@; const ResourceManagerProxy::`vftable'
0x180013330  mov     qword ptr [rax+8], 0
0x180013338  mov     [rax], rcx
0x18001333b  lea     rdx, [rax+8]
0x18001333f  lea     rcx, qword_18001D170; IfSpec
0x180013346  mov     cs:qword_18002ED78, rax
0x18001334d  call    CempRpcBindToServer
0x180013352  or      eax, 10000000h
0x180013357  mov     ebx, 0
0x18001335c  cmovl   ebx, eax
0x18001335f  test    ebx, ebx
0x180013361  js      short loc_180013367
0x180013363  xor     ebx, ebx
0x180013365  jmp     short loc_18001339E
0x180013367  mov     rcx, cs:qword_18002ED78
0x18001336e  jmp     short loc_18001337E
0x180013370  xor     ecx, ecx
0x180013372  mov     ebx, 8007000Eh
0x180013377  mov     cs:qword_18002ED78, rcx
0x18001337e  test    rcx, rcx
0x180013381  jz      short loc_18001339E
0x180013383  mov     rdx, [rcx]
0x180013386  mov     rax, [rdx]
0x180013389  mov     edx, 1
0x18001338e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013393  mov     cs:qword_18002ED78, 0
0x18001339e  mov     eax, ebx
0x1800133a0  add     rsp, 20h
0x1800133a4  pop     rbx
0x1800133a5  retn
```
