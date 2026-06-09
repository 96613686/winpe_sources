# CObjectArray::Create<IEnhancedStorageSilo>(IEnhancedStorageSilo * *,ulong,IObjectArray * *)

- ea: `0x18000a474`
- end: `0x18000a562`
- name: `??$Create@UIEnhancedStorageSilo@@@CObjectArray@@SAJPEAPEAUIEnhancedStorageSilo@@KPEAPEAUIObjectArray@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005dc0`
- `0x18000a890`

## callees

- `0x180006b8c`
- `0x18000a474`
- `0x18000a568`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CObjectArray::Create<IEnhancedStorageSilo>(__int64 a1, unsigned int a2, __int64 a3)
{
  char *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  _DWORD *v9; // rbx
  _QWORD *v10; // r14
  int v11; // edi
  unsigned int v12; // ebp
  __int64 v13; // rdi

  v6 = (char *)operator new(0x20u);
  v9 = v6;
  if ( !v6 )
    return 2147942414LL;
  *((_DWORD *)v6 + 2) = 1;
  *(_QWORD *)v6 = &CObjectArray::`vftable';
  *((_QWORD *)v6 + 2) = 0;
  *((_DWORD *)v6 + 6) = 0;
  v10 = v6 + 16;
  v11 = _AllocArray<IUnknown *,CTCoAllocPolicy>(v8, v7, a2, v6 + 16);
  if ( v11 >= 0 )
  {
    v12 = 0;
    v9[6] = a2;
    if ( a2 )
    {
      v13 = 0;
      do
      {
        *(_QWORD *)(*v10 + 8 * v13) = *(_QWORD *)(a1 + 8 * v13);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*v10 + 8 * v13) + 8LL))(*(_QWORD *)(*v10 + 8 * v13));
        ++v12;
        ++v13;
      }
      while ( v12 < a2 );
    }
    v11 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, __int64))v9)(
            v9,
            &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
            a3);
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a474  mov     [rsp+arg_0], rbx
0x18000a479  mov     [rsp+arg_8], rbp
0x18000a47e  push    rsi
0x18000a47f  push    rdi
0x18000a480  push    r12
0x18000a482  push    r14
0x18000a484  push    r15
0x18000a486  sub     rsp, 20h
0x18000a48a  mov     r12, rcx
0x18000a48d  mov     esi, edx
0x18000a48f  mov     ecx, 20h ; ' '; Size
0x18000a494  mov     r15, r8
0x18000a497  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a49c  mov     [rsp+48h+arg_18], rax
0x18000a4a1  mov     rbx, rax
0x18000a4a4  test    rax, rax
0x18000a4a7  jz      loc_18000A546
0x18000a4ad  mov     dword ptr [rbx+8], 1
0x18000a4b4  lea     rax, ??_7CObjectArray@@6B@; const CObjectArray::`vftable'
0x18000a4bb  mov     [rbx], rax
0x18000a4be  mov     qword ptr [rbx+10h], 0
0x18000a4c6  mov     dword ptr [rbx+18h], 0
0x18000a4cd  test    rbx, rbx
0x18000a4d0  jz      short loc_18000A546
0x18000a4d2  lea     r14, [rbx+10h]
0x18000a4d6  mov     r8d, esi
0x18000a4d9  mov     r9, r14
0x18000a4dc  call    ??$_AllocArray@PEAUIUnknown@@VCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAPEAUIUnknown@@@Z; _AllocArray<IUnknown *,CTCoAllocPolicy>(void *,ulong,unsigned __int64,IUnknown * * *)
0x18000a4e1  mov     edi, eax
0x18000a4e3  test    eax, eax
0x18000a4e5  js      short loc_18000A533
0x18000a4e7  xor     ebp, ebp
0x18000a4e9  mov     [rbx+18h], esi
0x18000a4ec  test    esi, esi
0x18000a4ee  jz      short loc_18000A519
0x18000a4f0  xor     edi, edi
0x18000a4f2  mov     rcx, [r14]
0x18000a4f5  mov     rax, [r12+rdi*8]
0x18000a4f9  mov     [rcx+rdi*8], rax
0x18000a4fd  mov     rax, [r14]
0x18000a500  mov     rcx, [rax+rdi*8]
0x18000a504  mov     rax, [rcx]
0x18000a507  mov     rax, [rax+8]
0x18000a50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a510  inc     ebp
0x18000a512  inc     rdi
0x18000a515  cmp     ebp, esi
0x18000a517  jb      short loc_18000A4F2
0x18000a519  mov     rax, [rbx]
0x18000a51c  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x18000a523  mov     r8, r15
0x18000a526  mov     rcx, rbx
0x18000a529  mov     rax, [rax]
0x18000a52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a531  mov     edi, eax
0x18000a533  mov     rax, [rbx]
0x18000a536  mov     rcx, rbx
0x18000a539  mov     rax, [rax+10h]
0x18000a53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a542  mov     eax, edi
0x18000a544  jmp     short loc_18000A54B
0x18000a546  mov     eax, 8007000Eh
0x18000a54b  mov     rbx, [rsp+48h+arg_0]
0x18000a550  mov     rbp, [rsp+48h+arg_8]
0x18000a555  add     rsp, 20h
0x18000a559  pop     r15
0x18000a55b  pop     r14
0x18000a55d  pop     r12
0x18000a55f  pop     rdi
0x18000a560  pop     rsi
0x18000a561  retn
```
