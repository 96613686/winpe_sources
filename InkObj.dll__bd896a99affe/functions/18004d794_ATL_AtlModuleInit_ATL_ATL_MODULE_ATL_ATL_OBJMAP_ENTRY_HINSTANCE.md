# ATL::AtlModuleInit(ATL::_ATL_MODULE *,ATL::_ATL_OBJMAP_ENTRY *,HINSTANCE__ *)

- ea: `0x18004d794`
- end: `0x18004d956`
- name: `?AtlModuleInit@ATL@@YAJPEAU_ATL_MODULE@1@PEAU_ATL_OBJMAP_ENTRY@1@PEAUHINSTANCE__@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(struct ATL::_ATL_MODULE *, struct ATL::_ATL_OBJMAP_ENTRY *, HINSTANCE)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800569a0`

## callees

- `0x18004d794`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004d7d9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004d7e7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004d7f5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004d7d9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004d7e7`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18004d7f5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d887`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d894`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d8f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d887`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d894`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004d8f2`

## pseudocode

```c
__int64 __fastcall ATL::AtlModuleInit(struct ATL::_ATL_MODULE *a1, struct ATL::_ATL_OBJMAP_ENTRY *a2, HINSTANCE a3)
{
  __int64 v3; // rcx
  __int64 v4; // rbx
  __int64 v5; // rax

  qword_18016D140 = (__int64)&off_18015F140;
  hInst = a3;
  hModule = a3;
  hInstance = a3;
  dword_18016D148 = 0;
  hHeap = 0;
  InitializeCriticalSection(&Buf1);
  InitializeCriticalSection(&stru_18016D180);
  InitializeCriticalSection(&stru_18016D1A8);
  qword_18016D1D8 = 0;
  byte_18016D1E0 = 1;
  dword_18016D1F0 = 0;
  dword_18016D200 = 0;
  qword_18016D1F8 = 0;
  qword_18016D208 = 0;
  v4 = qword_18016D140;
  if ( qword_18016D140 )
  {
    while ( *(_QWORD *)v4 )
    {
      LOBYTE(v3) = 1;
      (*(void (__fastcall **)(__int64))(v4 + 64))(v3);
      v5 = 72;
      v3 = 56;
      if ( _Module == 176 )
        v5 = 56;
      v4 += v5;
    }
  }
  dword_18016D210 = 1;
  return 0;
}

```

## disassembly

```asm
0x18004d794  push    rbx
0x18004d796  sub     rsp, 20h
0x18004d79a  lea     rax, off_18015F140
0x18004d7a1  mov     cs:qword_18016D140, rax
0x18004d7a8  mov     cs:hInst, r8
0x18004d7af  mov     cs:hModule, r8
0x18004d7b6  mov     cs:hInstance, r8
0x18004d7bd  mov     cs:dword_18016D148, 0
0x18004d7c7  mov     cs:hHeap, 0
0x18004d7d2  lea     rcx, Buf1; lpCriticalSection
0x18004d7d9  call    cs:__imp_InitializeCriticalSection
0x18004d7df  nop
0x18004d7e0  lea     rcx, stru_18016D180; lpCriticalSection
0x18004d7e7  call    cs:__imp_InitializeCriticalSection
0x18004d7ed  nop
0x18004d7ee  lea     rcx, stru_18016D1A8; lpCriticalSection
0x18004d7f5  call    cs:__imp_InitializeCriticalSection
0x18004d7fb  nop
0x18004d7fc  mov     cs:qword_18016D1D8, 0
0x18004d807  mov     cs:byte_18016D1E0, 1
0x18004d80e  mov     cs:dword_18016D1F0, 0
0x18004d818  mov     cs:dword_18016D200, 0
0x18004d822  mov     cs:qword_18016D1F8, 0
0x18004d82d  mov     cs:qword_18016D208, 0
0x18004d838  mov     rbx, cs:qword_18016D140
0x18004d83f  test    rbx, rbx
0x18004d842  jz      short loc_18004D86F
0x18004d844  jmp     short loc_18004D869
0x18004d846  mov     cl, 1
0x18004d848  mov     rax, [rbx+40h]
0x18004d84c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d851  mov     eax, 48h ; 'H'
0x18004d856  lea     ecx, [rax-10h]
0x18004d859  cmp     cs:?_Module@@3VCComDllModule@@A, 0B0h; CComDllModule _Module
0x18004d863  cmovz   eax, ecx
0x18004d866  add     rbx, rax
0x18004d869  cmp     qword ptr [rbx], 0
0x18004d86d  jnz     short loc_18004D846
0x18004d86f  mov     cs:dword_18016D210, 1
0x18004d879  xor     eax, eax
0x18004d87b  jmp     loc_18004D950
0x18004d880  lea     rcx, stru_18016D180; lpCriticalSection
0x18004d887  call    cs:__imp_DeleteCriticalSection
0x18004d88d  lea     rcx, Buf1; lpCriticalSection
0x18004d894  call    cs:__imp_DeleteCriticalSection
0x18004d89a  xorps   xmm0, xmm0
0x18004d89d  xor     eax, eax
0x18004d89f  movups  xmmword ptr cs:stru_18016D1A8.DebugInfo, xmm0
0x18004d8a6  movups  xmmword ptr cs:stru_18016D1A8.OwningThread, xmm0
0x18004d8ad  mov     cs:stru_18016D1A8.SpinCount, rax
0x18004d8b4  xorps   xmm1, xmm1
0x18004d8b7  movups  xmmword ptr cs:stru_18016D180.DebugInfo, xmm1
0x18004d8be  movups  xmmword ptr cs:stru_18016D180.OwningThread, xmm1
0x18004d8c5  mov     cs:stru_18016D180.SpinCount, rax
0x18004d8cc  xorps   xmm0, xmm0
0x18004d8cf  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x18004d8d6  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x18004d8dd  mov     cs:Buf1.SpinCount, rax
0x18004d8e4  mov     eax, 0C0000017h
0x18004d8e9  jmp     short loc_18004D950
0x18004d8eb  lea     rcx, Buf1; lpCriticalSection
0x18004d8f2  call    cs:__imp_DeleteCriticalSection
0x18004d8f8  xorps   xmm0, xmm0
0x18004d8fb  xor     eax, eax
0x18004d8fd  movups  xmmword ptr cs:stru_18016D180.DebugInfo, xmm0
0x18004d904  movups  xmmword ptr cs:stru_18016D180.OwningThread, xmm0
0x18004d90b  mov     cs:stru_18016D180.SpinCount, rax
0x18004d912  xorps   xmm1, xmm1
0x18004d915  movups  xmmword ptr cs:Buf1.DebugInfo, xmm1
0x18004d91c  movups  xmmword ptr cs:Buf1.OwningThread, xmm1
0x18004d923  mov     cs:Buf1.SpinCount, rax
0x18004d92a  mov     eax, 0C0000017h
0x18004d92f  jmp     short loc_18004D950
0x18004d931  xorps   xmm0, xmm0
0x18004d934  xor     eax, eax
0x18004d936  movups  xmmword ptr cs:Buf1.DebugInfo, xmm0
0x18004d93d  movups  xmmword ptr cs:Buf1.OwningThread, xmm0
0x18004d944  mov     cs:Buf1.SpinCount, rax
0x18004d94b  mov     eax, 0C0000017h
0x18004d950  add     rsp, 20h
0x18004d954  pop     rbx
0x18004d955  retn
0x1801087b5  push    rbp
0x1801087b7  sub     rsp, 20h
0x1801087bb  mov     rbp, rdx
0x1801087be  mov     rax, [rcx]
0x1801087c1  xor     ecx, ecx
0x1801087c3  cmp     dword ptr [rax], 0C0000017h
0x1801087c9  setz    cl
0x1801087cc  mov     eax, ecx
0x1801087ce  add     rsp, 20h
0x1801087d2  pop     rbp
0x1801087d3  retn
0x1801087d5  push    rbp
0x1801087d7  sub     rsp, 20h
0x1801087db  mov     rbp, rdx
0x1801087de  mov     rax, [rcx]
0x1801087e1  xor     ecx, ecx
0x1801087e3  cmp     dword ptr [rax], 0C0000017h
0x1801087e9  setz    cl
0x1801087ec  mov     eax, ecx
0x1801087ee  add     rsp, 20h
0x1801087f2  pop     rbp
0x1801087f3  retn
0x1801087f5  push    rbp
0x1801087f7  sub     rsp, 20h
0x1801087fb  mov     rbp, rdx
0x1801087fe  mov     rax, [rcx]
0x180108801  xor     ecx, ecx
0x180108803  cmp     dword ptr [rax], 0C0000017h
0x180108809  setz    cl
0x18010880c  mov     eax, ecx
0x18010880e  add     rsp, 20h
0x180108812  pop     rbp
0x180108813  retn
```
