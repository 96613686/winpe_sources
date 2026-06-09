# CBinaryAutoList::Save(IStream *,int)

- ea: `0x180043cf0`
- end: `0x180044101`
- name: `?Save@CBinaryAutoList@@UEAAJPEAUIStream@@H@Z`
- size: `1041`
- prototype: `int(CBinaryAutoList *__hidden this, struct IStream *, int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180043cf0`
- `0x180044108`
- `0x18004428c`
- `0x180044518`
- `0x1800448b4`
- `0x18004e270`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Write` at `0x180043d35`
- `SHCORE!IStream_Write` at `0x180043d79`
- `SHCORE!IStream_Write` at `0x180043de6`
- `SHCORE!IStream_Write` at `0x180043e99`
- `SHCORE!IStream_Write` at `0x180043f52`
- `SHCORE!IStream_Write` at `0x180043f87`
- `SHCORE!IStream_Write` at `0x180043fbc`
- `SHCORE!IStream_Write` at `0x180043fef`
- `SHCORE!IStream_Write` at `0x180044040`
- `SHCORE!IStream_Write` at `0x180043d35`
- `SHCORE!IStream_Write` at `0x180043d79`
- `SHCORE!IStream_Write` at `0x180043de6`
- `SHCORE!IStream_Write` at `0x180043e99`
- `SHCORE!IStream_Write` at `0x180043f52`
- `SHCORE!IStream_Write` at `0x180043f87`
- `SHCORE!IStream_Write` at `0x180043fbc`
- `SHCORE!IStream_Write` at `0x180043fef`
- `SHCORE!IStream_Write` at `0x180044040`

## pseudocode

```c
__int64 __fastcall CBinaryAutoList::Save(CBinaryAutoList *this, struct IStream *a2)
{
  CBinaryAutoList *v2; // r14
  int v5; // ebx
  __int64 v6; // rcx
  struct IUnknown *v7; // rcx
  __int64 v8; // rcx
  struct IUnknown *v9; // rcx
  __int64 v10; // rcx
  struct IUnknown *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  struct IUnknown *v16; // rcx
  struct IUnknown *v18[2]; // [rsp+30h] [rbp-10h] BYREF
  int pv; // [rsp+70h] [rbp+30h] BYREF
  struct IUnknown *v20; // [rsp+88h] [rbp+48h] BYREF

  v2 = (CBinaryAutoList *)((char *)this - 8);
  if ( *((_QWORD *)this + 3) )
  {
    pv = -2147483642;
    v5 = IStream_Write(a2, &pv, 4u);
    if ( v5 >= 0 )
    {
      v6 = *((_QWORD *)this + 3);
      v20 = 0;
      pv = (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v6 + 176LL))(
             v6,
             &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
             &v20) >= 0;
      v5 = IStream_Write(a2, &pv, 4u);
      if ( v5 >= 0 )
      {
        if ( pv )
        {
          v18[0] = 0;
          v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v20->lpVtbl->QueryInterface)(
                 v20,
                 &GUID_00000109_0000_0000_c000_000000000046,
                 v18);
          if ( v5 >= 0 )
          {
            v5 = IUnknown_SaveKnownImplToStream(a2, (const struct _GUID *const *)&off_1800EB330, 2u, v18[0]);
            ((void (__fastcall *)(struct IUnknown *))v18[0]->lpVtbl->Release)(v18[0]);
          }
        }
      }
      v7 = v20;
      v20 = 0;
      if ( v7 )
        ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
      if ( v5 >= 0 )
      {
        v8 = *((_QWORD *)this + 3);
        v20 = 0;
        pv = (*(int (__fastcall **)(__int64, _QWORD, GUID *, struct IUnknown **))(*(_QWORD *)v8 + 168LL))(
               v8,
               0,
               &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798,
               &v20) >= 0;
        v5 = IStream_Write(a2, &pv, 4u);
        if ( v5 >= 0 )
        {
          if ( pv )
          {
            v18[0] = 0;
            v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v20->lpVtbl->QueryInterface)(
                   v20,
                   &GUID_00000109_0000_0000_c000_000000000046,
                   v18);
            if ( v5 >= 0 )
            {
              v5 = ((__int64 (__fastcall *)(struct IUnknown *, struct IStream *, __int64))v18[0]->lpVtbl[2].QueryInterface)(
                     v18[0],
                     a2,
                     1);
              ((void (__fastcall *)(struct IUnknown *))v18[0]->lpVtbl->Release)(v18[0]);
            }
          }
        }
        v9 = v20;
        v20 = 0;
        if ( v9 )
          ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
        if ( v5 >= 0 )
        {
          v10 = *((_QWORD *)this + 3);
          v20 = 0;
          pv = (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v10 + 112LL))(
                 v10,
                 &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495,
                 &v20) >= 0;
          v5 = IStream_Write(a2, &pv, 4u);
          if ( v5 >= 0 )
          {
            if ( pv )
            {
              v18[0] = 0;
              v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v20->lpVtbl->QueryInterface)(
                     v20,
                     &GUID_00000109_0000_0000_c000_000000000046,
                     v18);
              if ( v5 >= 0 )
              {
                v5 = ((__int64 (__fastcall *)(struct IUnknown *, struct IStream *, __int64))v18[0]->lpVtbl[2].QueryInterface)(
                       v18[0],
                       a2,
                       1);
                ((void (__fastcall *)(struct IUnknown *))v18[0]->lpVtbl->Release)(v18[0]);
              }
            }
          }
          v11 = v20;
          v20 = 0;
          if ( v11 )
            ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
          if ( v5 >= 0 )
          {
            v5 = CBinaryAutoList::_SaveCondition(v2, a2);
            if ( v5 >= 0 )
            {
              v12 = *((_QWORD *)this + 3);
              pv = 0;
              (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 120LL))(v12, &pv);
              v5 = IStream_Write(a2, &pv, 4u);
              if ( v5 >= 0 )
              {
                v13 = *((_QWORD *)this + 3);
                LODWORD(v20) = 0;
                (*(void (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v13 + 128LL))(v13, &v20);
                v5 = IStream_Write(a2, &v20, 4u);
                if ( v5 >= 0 )
                {
                  v14 = *((_QWORD *)this + 3);
                  LODWORD(v20) = 0;
                  (*(void (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v14 + 136LL))(v14, &v20);
                  v5 = IStream_Write(a2, &v20, 4u);
                  if ( v5 >= 0 )
                  {
                    v5 = CBinaryAutoList::_SaveViewInfo(v2, a2);
                    if ( v5 >= 0 )
                    {
                      pv = 0;
                      v5 = IStream_Write(a2, &pv, 4u);
                      if ( v5 >= 0 )
                      {
                        v5 = CBinaryAutoList::_SaveColumnLists(v2, a2);
                        if ( v5 >= 0 )
                        {
                          v15 = *((_QWORD *)this + 3);
                          v20 = 0;
                          pv = (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v15 + 184LL))(
                                 v15,
                                 &GUID_00000000_0000_0000_c000_000000000046,
                                 &v20) >= 0;
                          v5 = IStream_Write(a2, &pv, 4u);
                          if ( v5 >= 0 && pv )
                            v5 = IUnknown_SaveToStream(a2, 1, v20);
                          v16 = v20;
                          v20 = 0;
                          if ( v16 )
                            ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->Release)(v16);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180043cf0  mov     [rsp-28h+arg_8], rbx
0x180043cf5  mov     [rsp-28h+arg_10], rsi
0x180043cfa  push    rbp
0x180043cfb  push    rdi
0x180043cfc  push    r12
0x180043cfe  push    r14
0x180043d00  push    r15
0x180043d02  mov     rbp, rsp
0x180043d05  sub     rsp, 40h
0x180043d09  lea     r14, [rcx-8]
0x180043d0d  xor     r15d, r15d
0x180043d10  mov     rdi, rdx
0x180043d13  mov     rsi, rcx
0x180043d16  cmp     [r14+20h], r15
0x180043d1a  jz      loc_18004408A
0x180043d20  lea     r12d, [r15+4]
0x180043d24  mov     [rbp+pv], 80000006h
0x180043d2b  mov     r8d, r12d; cb
0x180043d2e  lea     rdx, [rbp+pv]; pv
0x180043d32  mov     rcx, rdi; pstm
0x180043d35  call    cs:__imp_IStream_Write
0x180043d3b  mov     ebx, eax
0x180043d3d  test    eax, eax
0x180043d3f  js      loc_18004406F
0x180043d45  mov     rcx, [rsi+18h]
0x180043d49  lea     r8, [rbp+arg_18]
0x180043d4d  mov     [rbp+arg_18], r15
0x180043d51  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x180043d58  mov     rax, [rcx]
0x180043d5b  mov     rax, [rax+0B0h]
0x180043d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d67  not     eax
0x180043d69  lea     rdx, [rbp+pv]; pv
0x180043d6d  shr     eax, 1Fh
0x180043d70  mov     r8d, r12d; cb
0x180043d73  mov     rcx, rdi; pstm
0x180043d76  mov     [rbp+pv], eax
0x180043d79  call    cs:__imp_IStream_Write
0x180043d7f  mov     ebx, eax
0x180043d81  test    eax, eax
0x180043d83  js      short loc_180043D8F
0x180043d85  cmp     [rbp+pv], r15d
0x180043d89  jnz     loc_180044091
0x180043d8f  mov     rcx, [rbp+arg_18]
0x180043d93  mov     [rbp+arg_18], r15
0x180043d97  test    rcx, rcx
0x180043d9a  jz      short loc_180043DA8
0x180043d9c  mov     rax, [rcx]
0x180043d9f  mov     rax, [rax+10h]
0x180043da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043da8  test    ebx, ebx
0x180043daa  js      loc_18004406F
0x180043db0  mov     rcx, [rsi+18h]
0x180043db4  lea     r9, [rbp+arg_18]
0x180043db8  mov     [rbp+arg_18], r15
0x180043dbc  lea     r8, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x180043dc3  xor     edx, edx
0x180043dc5  mov     rax, [rcx]
0x180043dc8  mov     rax, [rax+0A8h]
0x180043dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043dd4  not     eax
0x180043dd6  lea     rdx, [rbp+pv]; pv
0x180043dda  shr     eax, 1Fh
0x180043ddd  mov     r8d, r12d; cb
0x180043de0  mov     rcx, rdi; pstm
0x180043de3  mov     [rbp+pv], eax
0x180043de6  call    cs:__imp_IStream_Write
0x180043dec  mov     ebx, eax
0x180043dee  test    eax, eax
0x180043df0  js      short loc_180043E47
0x180043df2  cmp     [rbp+pv], r15d
0x180043df6  jz      short loc_180043E47
0x180043df8  mov     rcx, [rbp+arg_18]
0x180043dfc  lea     r8, [rbp+var_10]
0x180043e00  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x180043e07  mov     [rbp+var_10], r15
0x180043e0b  mov     rax, [rcx]
0x180043e0e  mov     rax, [rax]
0x180043e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e16  mov     ebx, eax
0x180043e18  test    eax, eax
0x180043e1a  js      short loc_180043E47
0x180043e1c  mov     rcx, [rbp+var_10]
0x180043e20  mov     r8d, 1
0x180043e26  mov     rdx, rdi
0x180043e29  mov     rax, [rcx]
0x180043e2c  mov     rax, [rax+30h]
0x180043e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e35  mov     rcx, [rbp+var_10]
0x180043e39  mov     ebx, eax
0x180043e3b  mov     rax, [rcx]
0x180043e3e  mov     rax, [rax+10h]
0x180043e42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e47  mov     rcx, [rbp+arg_18]
0x180043e4b  mov     [rbp+arg_18], r15
0x180043e4f  test    rcx, rcx
0x180043e52  jz      short loc_180043E60
0x180043e54  mov     rax, [rcx]
0x180043e57  mov     rax, [rax+10h]
0x180043e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e60  test    ebx, ebx
0x180043e62  js      loc_18004406F
0x180043e68  mov     rcx, [rsi+18h]
0x180043e6c  lea     r8, [rbp+arg_18]
0x180043e70  mov     [rbp+arg_18], r15
0x180043e74  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x180043e7b  mov     rax, [rcx]
0x180043e7e  mov     rax, [rax+70h]
0x180043e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e87  not     eax
0x180043e89  lea     rdx, [rbp+pv]; pv
0x180043e8d  shr     eax, 1Fh
0x180043e90  mov     r8d, r12d; cb
0x180043e93  mov     rcx, rdi; pstm
0x180043e96  mov     [rbp+pv], eax
0x180043e99  call    cs:__imp_IStream_Write
0x180043e9f  mov     ebx, eax
0x180043ea1  test    eax, eax
0x180043ea3  js      short loc_180043EFA
0x180043ea5  cmp     [rbp+pv], r15d
0x180043ea9  jz      short loc_180043EFA
0x180043eab  mov     rcx, [rbp+arg_18]
0x180043eaf  lea     r8, [rbp+var_10]
0x180043eb3  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x180043eba  mov     [rbp+var_10], r15
0x180043ebe  mov     rax, [rcx]
0x180043ec1  mov     rax, [rax]
0x180043ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ec9  mov     ebx, eax
0x180043ecb  test    eax, eax
0x180043ecd  js      short loc_180043EFA
0x180043ecf  mov     rcx, [rbp+var_10]
0x180043ed3  mov     r8d, 1
0x180043ed9  mov     rdx, rdi
0x180043edc  mov     rax, [rcx]
0x180043edf  mov     rax, [rax+30h]
0x180043ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ee8  mov     rcx, [rbp+var_10]
0x180043eec  mov     ebx, eax
0x180043eee  mov     rax, [rcx]
0x180043ef1  mov     rax, [rax+10h]
0x180043ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043efa  mov     rcx, [rbp+arg_18]
0x180043efe  mov     [rbp+arg_18], r15
0x180043f02  test    rcx, rcx
0x180043f05  jz      short loc_180043F13
0x180043f07  mov     rax, [rcx]
0x180043f0a  mov     rax, [rax+10h]
0x180043f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f13  test    ebx, ebx
0x180043f15  js      loc_18004406F
0x180043f1b  mov     rdx, rdi; struct IStream *
0x180043f1e  mov     rcx, r14; this
0x180043f21  call    ?_SaveCondition@CBinaryAutoList@@AEAAJPEAUIStream@@@Z; CBinaryAutoList::_SaveCondition(IStream *)
0x180043f26  mov     ebx, eax
0x180043f28  test    eax, eax
0x180043f2a  js      loc_18004406F
0x180043f30  mov     rcx, [rsi+18h]
0x180043f34  lea     rdx, [rbp+pv]
0x180043f38  mov     [rbp+pv], r15d
0x180043f3c  mov     rax, [rcx]
0x180043f3f  mov     rax, [rax+78h]
0x180043f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f48  mov     r8d, r12d; cb
0x180043f4b  lea     rdx, [rbp+pv]; pv
0x180043f4f  mov     rcx, rdi; pstm
0x180043f52  call    cs:__imp_IStream_Write
0x180043f58  mov     ebx, eax
0x180043f5a  test    eax, eax
0x180043f5c  js      loc_18004406F
0x180043f62  mov     rcx, [rsi+18h]
0x180043f66  lea     rdx, [rbp+arg_18]
0x180043f6a  mov     dword ptr [rbp+arg_18], r15d
0x180043f6e  mov     rax, [rcx]
0x180043f71  mov     rax, [rax+80h]
0x180043f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f7d  mov     r8d, r12d; cb
0x180043f80  lea     rdx, [rbp+arg_18]; pv
0x180043f84  mov     rcx, rdi; pstm
0x180043f87  call    cs:__imp_IStream_Write
0x180043f8d  mov     ebx, eax
0x180043f8f  test    eax, eax
0x180043f91  js      loc_18004406F
0x180043f97  mov     rcx, [rsi+18h]
0x180043f9b  lea     rdx, [rbp+arg_18]
0x180043f9f  mov     dword ptr [rbp+arg_18], r15d
0x180043fa3  mov     rax, [rcx]
0x180043fa6  mov     rax, [rax+88h]
0x180043fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043fb2  mov     r8d, r12d; cb
0x180043fb5  lea     rdx, [rbp+arg_18]; pv
0x180043fb9  mov     rcx, rdi; pstm
0x180043fbc  call    cs:__imp_IStream_Write
0x180043fc2  mov     ebx, eax
0x180043fc4  test    eax, eax
0x180043fc6  js      loc_18004406F
0x180043fcc  mov     rdx, rdi; struct IStream *
0x180043fcf  mov     rcx, r14; this
0x180043fd2  call    ?_SaveViewInfo@CBinaryAutoList@@AEAAJPEAUIStream@@@Z; CBinaryAutoList::_SaveViewInfo(IStream *)
0x180043fd7  mov     ebx, eax
0x180043fd9  test    eax, eax
0x180043fdb  js      loc_18004406F
0x180043fe1  mov     r8d, r12d; cb
0x180043fe4  mov     [rbp+pv], r15d
0x180043fe8  lea     rdx, [rbp+pv]; pv
0x180043fec  mov     rcx, rdi; pstm
0x180043fef  call    cs:__imp_IStream_Write
0x180043ff5  mov     ebx, eax
0x180043ff7  test    eax, eax
0x180043ff9  js      short loc_18004406F
0x180043ffb  mov     rdx, rdi; struct IStream *
0x180043ffe  mov     rcx, r14; this
0x180044001  call    ?_SaveColumnLists@CBinaryAutoList@@AEAAJPEAUIStream@@@Z; CBinaryAutoList::_SaveColumnLists(IStream *)
0x180044006  mov     ebx, eax
0x180044008  test    eax, eax
0x18004400a  js      short loc_18004406F
0x18004400c  mov     rcx, [rsi+18h]
0x180044010  lea     r8, [rbp+arg_18]
0x180044014  mov     [rbp+arg_18], r15
0x180044018  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18004401f  mov     rax, [rcx]
0x180044022  mov     rax, [rax+0B8h]
0x180044029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004402e  not     eax
0x180044030  lea     rdx, [rbp+pv]; pv
0x180044034  shr     eax, 1Fh
0x180044037  mov     r8d, r12d; cb
0x18004403a  mov     rcx, rdi; pstm
0x18004403d  mov     [rbp+pv], eax
0x180044040  call    cs:__imp_IStream_Write
0x180044046  mov     ebx, eax
0x180044048  test    eax, eax
0x18004404a  js      short loc_180044056
0x18004404c  cmp     [rbp+pv], r15d
0x180044050  jnz     loc_1800440E9
0x180044056  mov     rcx, [rbp+arg_18]
0x18004405a  mov     [rbp+arg_18], r15
0x18004405e  test    rcx, rcx
0x180044061  jz      short loc_18004406F
0x180044063  mov     rax, [rcx]
0x180044066  mov     rax, [rax+10h]
0x18004406a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004406f  lea     r11, [rsp+40h+var_s0]
0x180044074  mov     eax, ebx
0x180044076  mov     rbx, [r11+38h]
0x18004407a  mov     rsi, [r11+40h]
0x18004407e  mov     rsp, r11
0x180044081  pop     r15
0x180044083  pop     r14
0x180044085  pop     r12
0x180044087  pop     rdi
0x180044088  pop     rbp
0x180044089  retn
0x18004408a  mov     ebx, 8000FFFFh
0x18004408f  jmp     short loc_18004406F
0x180044091  mov     rcx, [rbp+arg_18]
0x180044095  lea     r8, [rbp+var_10]
0x180044099  mov     [rbp+var_10], r15
0x18004409d  lea     rdx, _GUID_00000109_0000_0000_c000_000000000046
0x1800440a4  mov     rax, [rcx]
0x1800440a7  mov     rax, [rax]
0x1800440aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440af  mov     ebx, eax
0x1800440b1  test    eax, eax
0x1800440b3  js      loc_180043D8F
0x1800440b9  mov     r9, [rbp+var_10]; struct IUnknown *
0x1800440bd  lea     rdx, off_1800EB330; struct _GUID **
0x1800440c4  mov     r8d, 2; unsigned int
0x1800440ca  mov     rcx, rdi; pstm
0x1800440cd  call    ?IUnknown_SaveKnownImplToStream@@YAJPEAUIStream@@PEBQEBU_GUID@@IPEAUIUnknown@@@Z; IUnknown_SaveKnownImplToStream(IStream *,_GUID const * const *,uint,IUnknown *)
0x1800440d2  mov     rcx, [rbp+var_10]
0x1800440d6  mov     ebx, eax
0x1800440d8  mov     rax, [rcx]
0x1800440db  mov     rax, [rax+10h]
0x1800440df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440e4  jmp     loc_180043D8F
0x1800440e9  mov     r8, [rbp+arg_18]; struct IUnknown *
0x1800440ed  mov     edx, 1; int
0x1800440f2  mov     rcx, rdi; struct IStream *
0x1800440f5  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x1800440fa  mov     ebx, eax
0x1800440fc  jmp     loc_180044056
```
