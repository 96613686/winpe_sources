# CItemIDFactory<_ITEMID,1450709556>::s_CreateItemID(_ITEMID const *,IPropertyStore *,_ITEMIDLIST * *,IMalloc *)

- ea: `0x1800097f8`
- end: `0x180009958`
- name: `?s_CreateItemID@?$CItemIDFactory@U_ITEMID@@$0FGHIBCDE@@@SAJPEFBU_ITEMID@@PEAUIPropertyStore@@PEAPEFAU_ITEMIDLIST@@PEAUIMalloc@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180002c60`

## callees

- `0x1800097f8`
- `0x18000b5f2`
- `0x18000b5fe`
- `0x18000c010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000993f`
- `ole32!CoTaskMemFree` at `0x18000993f`
- `ole32!CoTaskMemAlloc` at `0x18000990e`
- `ole32!CoTaskMemAlloc` at `0x18000990e`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<_ITEMID,1450709556>::s_CreateItemID(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 *a3,
        __int64 a4)
{
  int v4; // eax
  int v8; // ebx
  __int64 v9; // rsi
  __int64 v10; // rbx
  __int16 v11; // di
  void *v12; // rax
  void *Src; // [rsp+20h] [rbp-10h] BYREF
  size_t Size; // [rsp+68h] [rbp+38h] BYREF
  __int64 v16; // [rsp+70h] [rbp+40h] BYREF

  v4 = 0;
  *a3 = 0;
  Src = 0;
  LODWORD(Size) = 0;
  if ( !a2 )
  {
LABEL_5:
    v9 = (unsigned int)(v4 + 20) + 2LL;
    if ( a4 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 24LL))(a4, (unsigned int)(v4 + 20) + 2LL);
    }
    else
    {
      v11 = v4 + 30;
      if ( (unsigned __int64)(unsigned int)(v4 + 20) + 10 > 0x10001 )
        goto LABEL_16;
      v12 = CoTaskMemAlloc((unsigned int)(v4 + 20) + 10LL);
      v10 = (__int64)v12;
      if ( v12 )
      {
        memset_0(v12, 0, v9 + 8);
        *(_WORD *)(v10 + 4) = v9;
        *(_WORD *)v10 = v11 - 2;
        goto LABEL_8;
      }
    }
    if ( v10 )
    {
LABEL_8:
      *(_DWORD *)(v10 + 6) = 1450709556;
      *(_WORD *)(v10 + 10) = Size;
      *(_WORD *)(v10 + 12) = 12;
      if ( a1 )
      {
        *(_QWORD *)(v10 + 14) = *(_QWORD *)a1;
        *(_DWORD *)(v10 + 22) = *(_DWORD *)(a1 + 8);
      }
      if ( Src )
        memcpy_0((void *)(v10 + 26), Src, (unsigned int)Size);
      *a3 = v10;
      v8 = 0;
      goto LABEL_17;
    }
LABEL_16:
    v8 = -2147024882;
LABEL_17:
    CoTaskMemFree(Src);
    return (unsigned int)v8;
  }
  v16 = 0;
  v8 = (**a2)(a2, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v16);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, void **, size_t *))(*(_QWORD *)v16 + 40LL))(v16, &Src, &Size);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v8 >= 0 )
    {
      v4 = Size;
      goto LABEL_5;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800097f8  mov     [rsp-28h+arg_0], rbx
0x1800097fd  push    rbp
0x1800097fe  push    rsi
0x1800097ff  push    rdi
0x180009800  push    r14
0x180009802  push    r15
0x180009804  mov     rbp, rsp
0x180009807  sub     rsp, 30h
0x18000980b  xor     eax, eax
0x18000980d  mov     qword ptr [r8], 0
0x180009814  mov     [rbp+Src], 0
0x18000981c  mov     rdi, r9
0x18000981f  mov     dword ptr [rbp+Size], eax
0x180009822  mov     r15, r8
0x180009825  mov     r10, rdx
0x180009828  mov     r14, rcx
0x18000982b  test    rdx, rdx
0x18000982e  jz      short loc_18000988C
0x180009830  mov     [rbp+arg_10], rax
0x180009834  lea     r8, [rbp+arg_10]
0x180009838  mov     rax, [rdx]
0x18000983b  mov     rcx, r10
0x18000983e  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x180009845  mov     rax, [rax]
0x180009848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000984d  mov     ebx, eax
0x18000984f  test    eax, eax
0x180009851  js      loc_180009945
0x180009857  mov     rcx, [rbp+arg_10]
0x18000985b  lea     r8, [rbp+Size]
0x18000985f  lea     rdx, [rbp+Src]
0x180009863  mov     rax, [rcx]
0x180009866  mov     rax, [rax+28h]
0x18000986a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000986f  mov     rcx, [rbp+arg_10]
0x180009873  mov     ebx, eax
0x180009875  mov     rax, [rcx]
0x180009878  mov     rax, [rax+10h]
0x18000987c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009881  test    ebx, ebx
0x180009883  js      loc_180009945
0x180009889  mov     eax, dword ptr [rbp+Size]
0x18000988c  lea     esi, [rax+14h]
0x18000988f  add     rsi, 2
0x180009893  test    rdi, rdi
0x180009896  jz      short loc_1800098FE
0x180009898  mov     rax, [rdi]
0x18000989b  mov     rdx, rsi
0x18000989e  mov     rcx, rdi
0x1800098a1  mov     rax, [rax+18h]
0x1800098a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098aa  mov     rbx, rax
0x1800098ad  test    rbx, rbx
0x1800098b0  jz      loc_180009936
0x1800098b6  mov     dword ptr [rbx+6], 56781234h
0x1800098bd  movzx   eax, word ptr [rbp+Size]
0x1800098c1  mov     [rbx+0Ah], ax
0x1800098c5  mov     word ptr [rbx+0Ch], 0Ch
0x1800098cb  test    r14, r14
0x1800098ce  jz      short loc_1800098E1
0x1800098d0  movsd   xmm0, qword ptr [r14]
0x1800098d5  movsd   qword ptr [rbx+0Eh], xmm0
0x1800098da  mov     eax, [r14+8]
0x1800098de  mov     [rbx+16h], eax
0x1800098e1  mov     rdx, [rbp+Src]; Src
0x1800098e5  test    rdx, rdx
0x1800098e8  jz      short loc_1800098F7
0x1800098ea  mov     r8d, dword ptr [rbp+Size]; Size
0x1800098ee  lea     rcx, [rbx+1Ah]; void *
0x1800098f2  call    memcpy_0
0x1800098f7  mov     [r15], rbx
0x1800098fa  xor     ebx, ebx
0x1800098fc  jmp     short loc_18000993B
0x1800098fe  lea     rdi, [rsi+8]
0x180009902  cmp     rdi, 10001h
0x180009909  ja      short loc_180009936
0x18000990b  mov     rcx, rdi; cb
0x18000990e  call    cs:__imp_CoTaskMemAlloc
0x180009914  mov     rbx, rax
0x180009917  test    rax, rax
0x18000991a  jz      short loc_1800098AD
0x18000991c  mov     r8, rdi; Size
0x18000991f  xor     edx, edx; Val
0x180009921  mov     rcx, rax; void *
0x180009924  call    memset_0
0x180009929  sub     di, 2
0x18000992d  mov     [rbx+4], si
0x180009931  mov     [rbx], di
0x180009934  jmp     short loc_1800098B6
0x180009936  mov     ebx, 8007000Eh
0x18000993b  mov     rcx, [rbp+Src]; pv
0x18000993f  call    cs:__imp_CoTaskMemFree
0x180009945  mov     eax, ebx
0x180009947  mov     rbx, [rsp+30h+arg_0]
0x18000994c  add     rsp, 30h
0x180009950  pop     r15
0x180009952  pop     r14
0x180009954  pop     rdi
0x180009955  pop     rsi
0x180009956  pop     rbp
0x180009957  retn
```
