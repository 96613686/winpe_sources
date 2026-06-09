# COMMAND_PROCESSOR::ExecuteCommand(ushort const *,ushort const *,ushort const *,ICommandParameterList *,ICommandObjectList * *,IXMLDOMDocument *,EXECUTION_FLAGS)

- ea: `0x1800074d0`
- end: `0x1800076e8`
- name: `?ExecuteCommand@COMMAND_PROCESSOR@@UEAAJPEBG00PEAVICommandParameterList@@PEAPEAVICommandObjectList@@PEAUIXMLDOMDocument@@W4EXECUTION_FLAGS@@@Z`
- size: `536`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001044`
- `0x1800054ec`
- `0x1800074d0`
- `0x18000e7ac`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::ExecuteCommand(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        OBJECT_LIST **a6,
        __int64 a7,
        int a8)
{
  struct IObjectExtension *v9; // r14
  OBJECT_LIST *v10; // rdi
  int ObjectExtension; // esi
  OBJECT_LIST *v12; // rax
  _DWORD *v13; // r12
  int v14; // eax
  unsigned int i; // ebx
  unsigned int v17; // [rsp+50h] [rbp-20h] BYREF
  int v18; // [rsp+54h] [rbp-1Ch]
  __int64 v19; // [rsp+58h] [rbp-18h] BYREF
  struct IObjectExtension *v20; // [rsp+60h] [rbp-10h] BYREF

  v20 = 0;
  v17 = 0;
  v9 = 0;
  v19 = 0;
  v10 = 0;
  if ( !a3 || !a2 || !a4 || !a5 || !a6 )
  {
    ObjectExtension = -2147024809;
    goto LABEL_23;
  }
  ObjectExtension = OBJECT_EXTENSION_TABLE::GetObjectExtension(*(OBJECT_EXTENSION_TABLE **)(a1 + 208), a2, a3, &v20);
  if ( ObjectExtension < 0 )
  {
LABEL_21:
    v9 = v20;
    goto LABEL_23;
  }
  v12 = (OBJECT_LIST *)operator new(0x70u);
  if ( !v12 || (v10 = OBJECT_LIST::OBJECT_LIST(v12)) == 0 )
  {
    ObjectExtension = -2147024888;
    goto LABEL_21;
  }
  v13 = (_DWORD *)(a1 + 336);
  v18 = *(_DWORD *)(a1 + 336);
  if ( a8 )
    *v13 = a8;
  v9 = v20;
  ++*(_DWORD *)(a1 + 356);
  v14 = (*(__int64 (__fastcall **)(struct IObjectExtension *, const unsigned __int16 *, const unsigned __int16 *, __int64, __int64, __int64, OBJECT_LIST *, __int64))(*(_QWORD *)v9 + 40LL))(
          v9,
          a2,
          a3,
          a4,
          (a1 + 8) & -(__int64)(a1 != 0),
          a5,
          v10,
          a7);
  --*(_DWORD *)(a1 + 356);
  ObjectExtension = v14;
  *v13 = v18;
  if ( v14 >= 0 )
  {
    if ( *a6 )
    {
      ObjectExtension = (*(__int64 (__fastcall **)(OBJECT_LIST *, unsigned int *))(*(_QWORD *)v10 + 32LL))(v10, &v17);
      if ( ObjectExtension >= 0 )
      {
        for ( i = 0; i < v17; ++i )
        {
          ObjectExtension = (*(__int64 (__fastcall **)(OBJECT_LIST *, _QWORD, __int64 *))(*(_QWORD *)v10 + 40LL))(
                              v10,
                              i,
                              &v19);
          if ( ObjectExtension < 0 )
            break;
          ObjectExtension = (*(__int64 (__fastcall **)(OBJECT_LIST *, __int64))(*(_QWORD *)*a6 + 24LL))(*a6, v19);
          if ( ObjectExtension < 0 )
            break;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          v19 = 0;
        }
      }
    }
    else
    {
      *a6 = v10;
      v10 = 0;
    }
  }
LABEL_23:
  if ( v19 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v19 = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(OBJECT_LIST *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v9 )
    (*(void (__fastcall **)(struct IObjectExtension *))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)ObjectExtension;
}

```

## disassembly

```asm
0x1800074d0  mov     rax, rsp
0x1800074d3  mov     [rax+8], rbx
0x1800074d7  mov     [rax+20h], r9
0x1800074db  mov     [rax+18h], r8
0x1800074df  mov     [rax+10h], rdx
0x1800074e3  push    rbp
0x1800074e4  push    rsi
0x1800074e5  push    rdi
0x1800074e6  push    r12
0x1800074e8  push    r13
0x1800074ea  push    r14
0x1800074ec  push    r15
0x1800074ee  mov     rbp, rsp
0x1800074f1  sub     rsp, 70h
0x1800074f5  xor     r12d, r12d
0x1800074f8  mov     rax, rdx
0x1800074fb  mov     [rbp+var_10], r12
0x1800074ff  mov     r13, rcx
0x180007502  mov     [rbp+var_20], r12d
0x180007506  mov     r14d, r12d
0x180007509  mov     [rbp+var_18], r12
0x18000750d  mov     edi, r12d
0x180007510  test    r8, r8
0x180007513  jz      loc_180007688
0x180007519  test    rax, rax
0x18000751c  jz      loc_180007688
0x180007522  test    r9, r9
0x180007525  jz      loc_180007688
0x18000752b  cmp     [rbp+arg_20], r12
0x18000752f  jz      loc_180007688
0x180007535  mov     r15, [rbp+arg_28]
0x180007539  test    r15, r15
0x18000753c  jz      loc_180007688
0x180007542  mov     rcx, [rcx+0D0h]; this
0x180007549  lea     r9, [rbp+var_10]; struct IObjectExtension **
0x18000754d  call    ?GetObjectExtension@OBJECT_EXTENSION_TABLE@@QEAAJPEBG0PEAPEAVIObjectExtension@@@Z; OBJECT_EXTENSION_TABLE::GetObjectExtension(ushort const *,ushort const *,IObjectExtension * *)
0x180007552  mov     esi, eax
0x180007554  test    eax, eax
0x180007556  js      loc_180007682
0x18000755c  lea     ecx, [r12+70h]; Size
0x180007561  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007566  test    rax, rax
0x180007569  jz      loc_18000767D
0x18000756f  mov     rcx, rax; this
0x180007572  call    ??0OBJECT_LIST@@QEAA@XZ; OBJECT_LIST::OBJECT_LIST(void)
0x180007577  mov     rdi, rax
0x18000757a  test    rax, rax
0x18000757d  jz      loc_18000767D
0x180007583  lea     r12, [r13+150h]
0x18000758a  mov     eax, [r12]
0x18000758e  mov     [rbp+var_1C], eax
0x180007591  mov     eax, [rbp+arg_38]
0x180007594  test    eax, eax
0x180007596  jz      short loc_18000759C
0x180007598  mov     [r12], eax
0x18000759c  mov     r14, [rbp+var_10]
0x1800075a0  lea     rax, [r13+8]
0x1800075a4  mov     r9, [rbp+arg_18]
0x1800075a8  lea     rbx, [r13+164h]
0x1800075af  inc     dword ptr [rbx]
0x1800075b1  mov     r8, [rbp+arg_10]
0x1800075b5  neg     r13
0x1800075b8  mov     rcx, [r14]
0x1800075bb  sbb     rdx, rdx
0x1800075be  and     rdx, rax
0x1800075c1  mov     rax, [rcx+28h]
0x1800075c5  mov     rcx, [rbp+arg_30]
0x1800075c9  mov     [rsp+70h+var_38], rcx
0x1800075ce  mov     rcx, [rbp+arg_20]
0x1800075d2  mov     [rsp+70h+var_40], rdi
0x1800075d7  mov     [rsp+70h+var_48], rcx
0x1800075dc  mov     rcx, r14
0x1800075df  mov     [rsp+70h+var_50], rdx
0x1800075e4  mov     rdx, [rbp+arg_8]
0x1800075e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075ed  dec     dword ptr [rbx]
0x1800075ef  mov     esi, eax
0x1800075f1  mov     eax, [rbp+var_1C]
0x1800075f4  mov     [r12], eax
0x1800075f8  xor     r12d, r12d
0x1800075fb  test    esi, esi
0x1800075fd  js      loc_18000768D
0x180007603  cmp     [r15], r12
0x180007606  jz      short loc_180007675
0x180007608  mov     rax, [rdi]
0x18000760b  lea     rdx, [rbp+var_20]
0x18000760f  mov     rcx, rdi
0x180007612  mov     rax, [rax+20h]
0x180007616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000761b  mov     esi, eax
0x18000761d  test    eax, eax
0x18000761f  js      short loc_18000768D
0x180007621  mov     ebx, r12d
0x180007624  cmp     ebx, [rbp+var_20]
0x180007627  jnb     short loc_18000768D
0x180007629  mov     rax, [rdi]
0x18000762c  lea     r8, [rbp+var_18]
0x180007630  mov     edx, ebx
0x180007632  mov     rcx, rdi
0x180007635  mov     rax, [rax+28h]
0x180007639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000763e  mov     esi, eax
0x180007640  test    eax, eax
0x180007642  js      short loc_18000768D
0x180007644  mov     rcx, [r15]
0x180007647  mov     rdx, [rbp+var_18]
0x18000764b  mov     rax, [rcx]
0x18000764e  mov     rax, [rax+18h]
0x180007652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007657  mov     esi, eax
0x180007659  test    eax, eax
0x18000765b  js      short loc_18000768D
0x18000765d  mov     rcx, [rbp+var_18]
0x180007661  mov     rax, [rcx]
0x180007664  mov     rax, [rax+10h]
0x180007668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000766d  inc     ebx
0x18000766f  mov     [rbp+var_18], r12
0x180007673  jmp     short loc_180007624
0x180007675  mov     [r15], rdi
0x180007678  mov     rdi, r12
0x18000767b  jmp     short loc_18000768D
0x18000767d  mov     esi, 80070008h
0x180007682  mov     r14, [rbp+var_10]
0x180007686  jmp     short loc_18000768D
0x180007688  mov     esi, 80070057h
0x18000768d  mov     rcx, [rbp+var_18]
0x180007691  test    rcx, rcx
0x180007694  jz      short loc_1800076A6
0x180007696  mov     rax, [rcx]
0x180007699  mov     rax, [rax+10h]
0x18000769d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076a2  mov     [rbp+var_18], r12
0x1800076a6  test    rdi, rdi
0x1800076a9  jz      short loc_1800076BA
0x1800076ab  mov     rax, [rdi]
0x1800076ae  mov     rcx, rdi
0x1800076b1  mov     rax, [rax+10h]
0x1800076b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ba  test    r14, r14
0x1800076bd  jz      short loc_1800076CE
0x1800076bf  mov     rax, [r14]
0x1800076c2  mov     rcx, r14
0x1800076c5  mov     rax, [rax+10h]
0x1800076c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ce  mov     rbx, [rsp+70h+arg_0]
0x1800076d6  mov     eax, esi
0x1800076d8  add     rsp, 70h
0x1800076dc  pop     r15
0x1800076de  pop     r14
0x1800076e0  pop     r13
0x1800076e2  pop     r12
0x1800076e4  pop     rdi
0x1800076e5  pop     rsi
0x1800076e6  pop     rbp
0x1800076e7  retn
```
