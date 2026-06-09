# RecordRegScanFailures(REGISTRY_SCAN_FUNC_ARGS *,ushort const *,long,uint)

- ea: `0x180024660`
- end: `0x180024754`
- name: `?RecordRegScanFailures@@YAJPEAUREGISTRY_SCAN_FUNC_ARGS@@PEBGJI@Z`
- size: `244`
- prototype: `__int64 __fastcall(struct REGISTRY_SCAN_FUNC_ARGS *, const unsigned __int16 *, int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180024278`
- `0x18002475c`
- `0x180024938`

## callees

- `0x1800152d4`
- `0x18001f218`
- `0x18001f4a0`
- `0x180024660`
- `0x180025388`

## string_xrefs

- `0x180024699`: `<EmptyRegPath>`

## pseudocode

```c
__int64 __fastcall RecordRegScanFailures(
        struct REGISTRY_SCAN_FUNC_ARGS *a1,
        const unsigned __int16 *a2,
        int a3,
        int a4)
{
  unsigned __int16 v8; // ax
  __int64 v9; // r8
  unsigned __int16 v10; // cx
  unsigned int v11; // edx
  const unsigned __int16 *v12; // rsi
  unsigned int v13; // ecx
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 2 * wcsnlen_s(a2, 0x4000u);
  if ( v8 )
    v10 = v8;
  else
    v10 = 28;
  v11 = *((unsigned __int16 *)a1 + 29);
  v12 = L"<EmptyRegPath>";
  if ( v8 )
    v12 = a2;
  v13 = v10 + 6;
  if ( v13 <= v11 )
  {
    if ( *((_WORD *)a1 + 24) >= 0xC8u || v13 + *((unsigned __int16 *)a1 + 28) > v11 )
      WriteRegScanFailureBuffer(a1);
    v15 = CopyBuffer((struct _UNICODE_STRING *)((char *)a1 + 56), v12, v9, 0x4000u);
    v16 = v15;
    if ( v15 >= 0 )
    {
      v17 = *((unsigned __int16 *)a1 + 24);
      *(_DWORD *)(*((_QWORD *)a1 + 9) + 4 * v17) = a3;
      *(_DWORD *)(*((_QWORD *)a1 + 10) + 4 * v17) = *(_DWORD *)a1;
      *(_DWORD *)(*((_QWORD *)a1 + 11) + 4 * v17) = a4;
      ++*((_WORD *)a1 + 24);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A5,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\regscanner.cpp",
        (const char *)(unsigned int)v15,
        v18);
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19C,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\regscanner.cpp",
      (const char *)0x8007000ELL,
      v18);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180024660  push    rbx
0x180024662  push    rbp
0x180024663  push    rsi
0x180024664  push    rdi
0x180024665  push    r12
0x180024667  push    r14
0x180024669  sub     rsp, 28h
0x18002466d  mov     rdi, rdx
0x180024670  mov     rbx, rcx
0x180024673  mov     rcx, rdi; Source
0x180024676  mov     edx, 4000h; MaxCount
0x18002467b  mov     ebp, r9d
0x18002467e  mov     r14d, r8d
0x180024681  call    wcsnlen_s
0x180024686  add     ax, ax
0x180024689  jnz     short loc_180024692
0x18002468b  mov     ecx, 1Ch
0x180024690  jmp     short loc_180024695
0x180024692  movzx   ecx, ax
0x180024695  movzx   edx, word ptr [rbx+3Ah]
0x180024699  lea     rsi, aEmptyregpath; "<EmptyRegPath>"
0x1800246a0  test    ax, ax
0x1800246a3  movzx   ecx, cx
0x1800246a6  cmovnz  rsi, rdi
0x1800246aa  add     ecx, 6
0x1800246ad  cmp     ecx, edx
0x1800246af  jbe     short loc_1800246D3
0x1800246b1  mov     rcx, [rsp+58h]; this
0x1800246b6  lea     r8, aOnecoreDrivers_3; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800246bd  mov     ebx, 8007000Eh
0x1800246c2  mov     edx, 19Ch; void *
0x1800246c7  mov     r9d, ebx; char *
0x1800246ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246cf  mov     eax, ebx
0x1800246d1  jmp     short loc_180024747
0x1800246d3  mov     eax, 0C8h
0x1800246d8  cmp     [rbx+30h], ax
0x1800246dc  jnb     short loc_1800246E8
0x1800246de  movzx   eax, word ptr [rbx+38h]
0x1800246e2  add     eax, ecx
0x1800246e4  cmp     eax, edx
0x1800246e6  jbe     short loc_1800246F0
0x1800246e8  mov     rcx, rbx; struct REGISTRY_SCAN_FUNC_ARGS *
0x1800246eb  call    ?WriteRegScanFailureBuffer@@YAXPEAUREGISTRY_SCAN_FUNC_ARGS@@@Z; WriteRegScanFailureBuffer(REGISTRY_SCAN_FUNC_ARGS *)
0x1800246f0  mov     r9d, 4000h; unsigned int
0x1800246f6  lea     rcx, [rbx+38h]; struct _UNICODE_STRING *
0x1800246fa  mov     rdx, rsi; unsigned __int16 *
0x1800246fd  call    ?CopyBuffer@@YAJPEAU_UNICODE_STRING@@PEBGGK@Z; CopyBuffer(_UNICODE_STRING *,ushort const *,ushort,ulong)
0x180024702  mov     edi, eax
0x180024704  test    eax, eax
0x180024706  jns     short loc_180024725
0x180024708  mov     rcx, [rsp+58h]; this
0x18002470d  lea     r8, aOnecoreDrivers_3; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180024714  mov     r9d, eax; char *
0x180024717  mov     edx, 1A5h; void *
0x18002471c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024721  mov     eax, edi
0x180024723  jmp     short loc_180024747
0x180024725  mov     rax, [rbx+48h]
0x180024729  movzx   edx, word ptr [rbx+30h]
0x18002472d  mov     [rax+rdx*4], r14d
0x180024731  mov     eax, [rbx]
0x180024733  mov     rcx, [rbx+50h]
0x180024737  mov     [rcx+rdx*4], eax
0x18002473a  mov     rax, [rbx+58h]
0x18002473e  mov     [rax+rdx*4], ebp
0x180024741  inc     word ptr [rbx+30h]
0x180024745  xor     eax, eax
0x180024747  add     rsp, 28h
0x18002474b  pop     r14
0x18002474d  pop     r12
0x18002474f  pop     rdi
0x180024750  pop     rsi
0x180024751  pop     rbp
0x180024752  pop     rbx
0x180024753  retn
```
