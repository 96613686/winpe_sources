# CGraphicsCommandList::ExecuteIndirect(ID3D12CommandSignature *,uint,ID3D12Resource *,unsigned __int64,ID3D12Resource *,unsigned __int64)

- ea: `0x180258cb0`
- end: `0x180259304`
- name: `?ExecuteIndirect@CGraphicsCommandList@@QEAAXPEAUID3D12CommandSignature@@IPEAUID3D12Resource@@_K12@Z`
- size: `1620`
- prototype: `void __fastcall(CGraphicsCommandList *__hidden this, struct ID3D12CommandSignature *, unsigned int, struct ID3D12Resource *, unsigned __int64, struct ID3D12Resource *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18024e440`

## callees

- `0x180128200`
- `0x180131884`
- `0x180245c18`
- `0x180246be8`
- `0x180258cb0`

## string_xrefs

- `0x180258d92`: `The source resource cannot be on a D3D12_HEAP_TYPE_READBACK heap.`
- `0x180258e70`: `The source resource cannot be on a D3D12_HEAP_TYPE_READBACK heap.`
- `0x180258f49`: `ExecuteIndirect does not support Draw* operations on a compute command list.`
- `0x180258f26`: `Node mask mismatch between command signature and command list.`
- `0x180258d08`: `ExecuteIndirect can only be called on a bundle when the count buffer is set to NULL, and the command signature contains exactly 1 parameter (which must be a Draw, DrawIndexed, Dispatch or DispatchRays).`

## pseudocode

```c
void __fastcall CGraphicsCommandList::ExecuteIndirect(
        CGraphicsCommandList *this,
        struct ID3D12CommandSignature *a2,
        unsigned int a3,
        struct ID3D12Resource *a4,
        unsigned __int64 a5,
        struct ID3D12Resource *a6,
        unsigned __int64 a7)
{
  struct ID3D12Resource *v11; // rbx
  bool v12; // r12
  __int64 v13; // r14
  int v14; // ecx
  ID3D12Resource_vtbl *v15; // rcx
  int v16; // ecx
  __int64 v17; // rcx
  _QWORD *v18; // rax
  __int64 v19; // r8
  ID3D12CommandSignature_vtbl *v20; // r14
  __int64 v21; // rbp
  unsigned int v22; // esi
  __int64 v23; // rbx
  _DWORD *v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rdx
  unsigned __int64 v28; // r11
  __int64 v29; // r10
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rdx
  unsigned __int64 v33; // r10
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v36; // rdx
  unsigned __int64 v37; // r10
  __int64 v38; // r9
  __int64 v39; // rcx
  __int64 v40; // rdx
  unsigned __int64 v41; // r10
  __int64 v42; // r9
  __int64 v43; // rcx
  int v44; // r8d
  __int64 v45; // rcx
  int v46; // [rsp+20h] [rbp-88h]
  _QWORD v47[2]; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v48[11]; // [rsp+50h] [rbp-58h] BYREF

  v11 = a6;
  v12 = ((__int64)a2[28].__vftable & 0xFFFFFFFD) == 0;
  if ( *((_DWORD *)this + 70) == 1
    && (a6 || (unsigned int)(((char *)a2[26].__vftable - (char *)a2[25].__vftable) >> 4) != 1) )
  {
    CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(
      this,
      744,
      2147942487LL,
      "ExecuteIndirect can only be called on a bundle when the count buffer is set to NULL, and the command signature con"
      "tains exactly 1 parameter (which must be a Draw, DrawIndexed, Dispatch or DispatchRays).");
  }
  v13 = a7;
  if ( (((unsigned __int8)a7 | (unsigned __int8)a5) & 3) != 0 )
    CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(
      this,
      744,
      2147942487LL,
      "Argument buffer & count buffer offsets must be 4 byte aligned.");
  if ( ((__int64)a4[29].__vftable & 0xF000000) != 0x1000000 )
    CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(
      this,
      744,
      2147942487LL,
      "Argument and count resources must be buffers.");
  if ( (HIDWORD(a4[29].__vftable) & 0xF000000) == 0x3000000 )
    CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(
      this,
      744,
      2147942487LL,
      "The source resource cannot be on a D3D12_HEAP_TYPE_READBACK heap.");
  if ( a4[24].__vftable )
    CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(
      this,
      744,
      2147942487LL,
      "The argument resource cannot be a protected resource.");
  v14 = (int)a4[29].__vftable;
  if ( (v14 & 0xF000000) == 0x1000000 )
    v15 = a4[28].__vftable;
  else
    v15 = (ID3D12Resource_vtbl *)(v14 & 0xFFFFFF);
  CCastableCommandList<ID3D12VideoProcessCommandList4>::ValidateSize(
    (_DWORD)this,
    HIDWORD(a2[28].__vftable),
    a2[29].__vftable,
    a3,
    a5,
    (__int64)v15,
    744,
    (__int64)"The argument resource is too small for ExecuteIndirect's [stride * count + offset].");
  if ( v11 )
  {
    if ( ((__int64)v11[29].__vftable & 0xF000000) != 0x1000000 )
      CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(
        this,
        744,
        2147942487LL,
        "Argument and count resources must be buffers.");
    if ( (HIDWORD(v11[29].__vftable) & 0xF000000) == 0x3000000 )
      CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(
        this,
        744,
        2147942487LL,
        "The source resource cannot be on a D3D12_HEAP_TYPE_READBACK heap.");
    if ( v11[24].__vftable )
      CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(
        this,
        744,
        2147942487LL,
        "The count resource cannot be a protected resource.");
    v16 = (int)v11[29].__vftable;
    if ( (v16 & 0xF000000) == 0x1000000 )
      v17 = (__int64)v11[28].__vftable;
    else
      v17 = v16 & 0xFFFFFF;
    CCastableCommandList<ID3D12VideoProcessCommandList4>::ValidateSize(
      (_DWORD)this,
      4,
      4,
      1,
      v13,
      v17,
      744,
      (__int64)"Count buffer overflow.");
  }
  else if ( v13 )
  {
    CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(
      this,
      744,
      2147942487LL,
      "If no count buffer is specified, the count buffer offset must be 0.");
  }
  CCastableCommandList<ID3D12GraphicsCommandList11>::ValidateNodeMask(
    this,
    HIDWORD(a2[29].__vftable),
    "Node mask mismatch between command signature and command list.");
  if ( *((_DWORD *)this + 70) == 2 && !v12 )
    CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(
      this,
      744,
      2147942487LL,
      "ExecuteIndirect does not support Draw* operations on a compute command list.");
  v18 = (_QWORD *)CCommandList<ID3D12GraphicsCommandList11>::DDIHandle(this, &a6);
  v47[0] = v19;
  v47[1] = v13;
  v48[0] = a4 + 52;
  v48[1] = a5;
  (*(void (__fastcall **)(_QWORD, struct ID3D12CommandSignature *, _QWORD, _QWORD *, _QWORD *))(((*((_QWORD *)this + 46)
                                                                                                + 128LL)
                                                                                               & ((1LL << (char)g_TableAndSize)
                                                                                                - 1))
                                                                                              + ((unsigned __int64)g_TableAndSize
                                                                                               & 0xFFFFFFFFFFFF0000uLL)))(
    *v18,
    a2 + 30,
    a3,
    v48,
    v47);
  v20 = a2[25].__vftable;
  v21 = ((char *)a2[26].__vftable - (char *)v20) >> 4;
  v22 = 0;
  if ( (_DWORD)v21 )
  {
    v23 = 0;
    do
    {
      v24 = (_DWORD *)v20 + 4 * v23;
      switch ( *v24 )
      {
        case 3:
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(((*((_QWORD *)this + 46) + 368LL)
                                                                      & ((1LL << (char)g_TableAndSize) - 1))
                                                                     + ((unsigned __int64)g_TableAndSize
                                                                      & 0xFFFFFFFFFFFF0000uLL)))(
            *((_QWORD *)this + 34),
            (unsigned int)v24[1],
            1,
            qword_1802FB520);
          break;
        case 4:
          (*(void (__fastcall **)(_QWORD, _QWORD))(((*((_QWORD *)this + 46) + 360LL)
                                                  & ((1LL << (char)g_TableAndSize) - 1))
                                                 + ((unsigned __int64)g_TableAndSize & 0xFFFFFFFFFFFF0000uLL)))(
            *((_QWORD *)this + 34),
            0);
          break;
        case 5:
          v25 = (unsigned int)v24[3];
          v26 = *((_QWORD *)this + 34);
          v46 = v24[2];
          v27 = (unsigned int)v24[1];
          v28 = (unsigned __int64)g_TableAndSize & 0xFFFFFFFFFFFF0000uLL;
          v29 = (1LL << (char)g_TableAndSize) - 1;
          v30 = *((_QWORD *)this + 46);
          if ( v12 )
            v31 = v30 + 296;
          else
            v31 = v30 + 304;
          goto LABEL_53;
        case 6:
          v32 = (unsigned int)v24[1];
          v33 = (unsigned __int64)g_TableAndSize & 0xFFFFFFFFFFFF0000uLL;
          v34 = (1LL << (char)g_TableAndSize) - 1;
          v35 = *((_QWORD *)this + 46);
          if ( v12 )
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(((v35 + 312) & v34) + v33))(
              *((_QWORD *)this + 34),
              v32,
              0);
          else
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(((v35 + 320) & v34) + v33))(
              *((_QWORD *)this + 34),
              v32,
              0);
          break;
        case 7:
          v36 = (unsigned int)v24[1];
          v37 = (unsigned __int64)g_TableAndSize & 0xFFFFFFFFFFFF0000uLL;
          v38 = (1LL << (char)g_TableAndSize) - 1;
          v39 = *((_QWORD *)this + 46);
          if ( v12 )
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(((v39 + 328) & v38) + v37))(
              *((_QWORD *)this + 34),
              v36,
              0);
          else
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(((v39 + 336) & v38) + v37))(
              *((_QWORD *)this + 34),
              v36,
              0);
          break;
        case 8:
          v40 = (unsigned int)v24[1];
          v41 = (unsigned __int64)g_TableAndSize & 0xFFFFFFFFFFFF0000uLL;
          v42 = (1LL << (char)g_TableAndSize) - 1;
          v43 = *((_QWORD *)this + 46);
          if ( v12 )
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(((v43 + 344) & v42) + v41))(
              *((_QWORD *)this + 34),
              v40,
              0);
          else
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(((v43 + 352) & v42) + v41))(
              *((_QWORD *)this + 34),
              v40,
              0);
          break;
        case 0xB:
          v44 = v24[2];
          v26 = *((_QWORD *)this + 34);
          v27 = (unsigned int)v24[1];
          v46 = v44;
          v25 = 1;
          v29 = (1LL << (char)g_TableAndSize) - 1;
          v45 = *((_QWORD *)this + 46);
          if ( v12 )
            v31 = v45 + 296;
          else
            v31 = v45 + 304;
          v28 = (unsigned __int64)g_TableAndSize & 0xFFFFFFFFFFFF0000uLL;
LABEL_53:
          (*(void (__fastcall **)(__int64, __int64, __int64, __int64 *, int))((v31 & v29) + v28))(
            v26,
            v27,
            v25,
            qword_1802FAF60,
            v46);
          break;
        default:
          break;
      }
      ++v22;
      ++v23;
    }
    while ( v22 < (unsigned int)v21 );
  }
}

```

## disassembly

```asm
0x180258cb0  push    rbx
0x180258cb2  push    rbp
0x180258cb3  push    rsi
0x180258cb4  push    rdi
0x180258cb5  push    r12
0x180258cb7  push    r13
0x180258cb9  push    r14
0x180258cbb  push    r15
0x180258cbd  sub     rsp, 68h
0x180258cc1  mov     rsi, r9
0x180258cc4  mov     r13d, r8d
0x180258cc7  mov     rbp, rdx
0x180258cca  mov     rdi, rcx
0x180258ccd  mov     rbx, [rsp+0A8h+arg_28]
0x180258cd5  test    dword ptr [rdx+0E0h], 0FFFFFFFDh
0x180258cdf  setz    r12b
0x180258ce3  cmp     dword ptr [rcx+118h], 1
0x180258cea  jnz     short loc_180258D1F
0x180258cec  test    rbx, rbx
0x180258cef  jnz     short loc_180258D08
0x180258cf1  mov     rax, [rdx+0D0h]
0x180258cf8  sub     rax, [rdx+0C8h]
0x180258cff  sar     rax, 4
0x180258d03  cmp     eax, 1
0x180258d06  jz      short loc_180258D1F
0x180258d08  lea     r9, aExecuteindirec; "ExecuteIndirect can only be called on a"...
0x180258d0f  mov     edx, 2E8h
0x180258d14  mov     r8d, 80070057h
0x180258d1a  call    ?RemoveCommandList@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXW4D3D12_MESSAGE_ID@@JPEBD_K@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(D3D12_MESSAGE_ID,long,char const *,unsigned __int64)
0x180258d1f  mov     r15, [rsp+0A8h+arg_20]
0x180258d27  movzx   eax, r15b
0x180258d2b  mov     r14, [rsp+0A8h+arg_30]
0x180258d33  or      al, r14b
0x180258d36  test    al, 3
0x180258d38  jz      short loc_180258D54
0x180258d3a  lea     r9, aArgumentBuffer; "Argument buffer & count buffer offsets "...
0x180258d41  mov     edx, 2E8h
0x180258d46  mov     r8d, 80070057h
0x180258d4c  mov     rcx, rdi
0x180258d4f  call    ?RemoveCommandList@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXW4D3D12_MESSAGE_ID@@JPEBD_K@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(D3D12_MESSAGE_ID,long,char const *,unsigned __int64)
0x180258d54  mov     eax, [rsi+0E8h]
0x180258d5a  and     eax, 0F000000h
0x180258d5f  cmp     eax, 1000000h
0x180258d64  jz      short loc_180258D80
0x180258d66  lea     r9, aArgumentAndCou; "Argument and count resources must be bu"...
0x180258d6d  mov     edx, 2E8h
0x180258d72  mov     r8d, 80070057h
0x180258d78  mov     rcx, rdi
0x180258d7b  call    ?RemoveCommandList@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXW4D3D12_MESSAGE_ID@@JPEBD_K@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(D3D12_MESSAGE_ID,long,char const *,unsigned __int64)
0x180258d80  mov     eax, [rsi+0ECh]
0x180258d86  and     eax, 0F000000h
0x180258d8b  cmp     eax, 3000000h
0x180258d90  jnz     short loc_180258DAC
0x180258d92  lea     r9, aTheSourceResou_0; "The source resource cannot be on a D3D1"...
0x180258d99  mov     edx, 2E8h
0x180258d9e  mov     r8d, 80070057h
0x180258da4  mov     rcx, rdi
0x180258da7  call    ?RemoveCommandList@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXW4D3D12_MESSAGE_ID@@JPEBD_K@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(D3D12_MESSAGE_ID,long,char const *,unsigned __int64)
0x180258dac  cmp     qword ptr [rsi+0C0h], 0
0x180258db4  jz      short loc_180258DD0
0x180258db6  lea     r9, aTheArgumentRes; "The argument resource cannot be a prote"...
0x180258dbd  mov     edx, 2E8h
0x180258dc2  mov     r8d, 80070057h
0x180258dc8  mov     rcx, rdi
0x180258dcb  call    ?RemoveCommandList@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXW4D3D12_MESSAGE_ID@@JPEBD_K@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(D3D12_MESSAGE_ID,long,char const *,unsigned __int64)
0x180258dd0  mov     ecx, [rsi+0E8h]
0x180258dd6  mov     eax, ecx
0x180258dd8  and     eax, 0F000000h
0x180258ddd  cmp     eax, 1000000h
0x180258de2  jnz     short loc_180258DED
0x180258de4  mov     rcx, [rsi+0E0h]
0x180258deb  jmp     short loc_180258DF3
0x180258ded  and     ecx, 0FFFFFFh
0x180258df3  lea     rax, aTheArgumentRes_0; "The argument resource is too small for "...
0x180258dfa  mov     [rsp+0A8h+var_70], rax
0x180258dff  mov     [rsp+0A8h+var_78], 2E8h
0x180258e07  mov     [rsp+0A8h+var_80], rcx
0x180258e0c  mov     [rsp+0A8h+var_88], r15
0x180258e11  mov     r9d, r13d
0x180258e14  mov     r8d, [rbp+0E8h]
0x180258e1b  mov     edx, [rbp+0E4h]
0x180258e21  mov     rcx, rdi
0x180258e24  call    ?ValidateSize@?$CCastableCommandList@UID3D12VideoProcessCommandList4@@@@IEAAXIII_K0W4D3D12_MESSAGE_ID@@PEBD@Z; CCastableCommandList<ID3D12VideoProcessCommandList4>::ValidateSize(uint,uint,uint,unsigned __int64,unsigned __int64,D3D12_MESSAGE_ID,char const *)
0x180258e29  test    rbx, rbx
0x180258e2c  jz      loc_180258F07
0x180258e32  mov     eax, [rbx+0E8h]
0x180258e38  and     eax, 0F000000h
0x180258e3d  cmp     eax, 1000000h
0x180258e42  jz      short loc_180258E5E
0x180258e44  lea     r9, aArgumentAndCou; "Argument and count resources must be bu"...
0x180258e4b  mov     edx, 2E8h
0x180258e50  mov     r8d, 80070057h
0x180258e56  mov     rcx, rdi
0x180258e59  call    ?RemoveCommandList@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXW4D3D12_MESSAGE_ID@@JPEBD_K@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(D3D12_MESSAGE_ID,long,char const *,unsigned __int64)
0x180258e5e  mov     eax, [rbx+0ECh]
0x180258e64  and     eax, 0F000000h
0x180258e69  cmp     eax, 3000000h
0x180258e6e  jnz     short loc_180258E8A
0x180258e70  lea     r9, aTheSourceResou_0; "The source resource cannot be on a D3D1"...
0x180258e77  mov     edx, 2E8h
0x180258e7c  mov     r8d, 80070057h
0x180258e82  mov     rcx, rdi
0x180258e85  call    ?RemoveCommandList@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXW4D3D12_MESSAGE_ID@@JPEBD_K@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(D3D12_MESSAGE_ID,long,char const *,unsigned __int64)
0x180258e8a  cmp     qword ptr [rbx+0C0h], 0
0x180258e92  jz      short loc_180258EAE
0x180258e94  lea     r9, aTheCountResour; "The count resource cannot be a protecte"...
0x180258e9b  mov     edx, 2E8h
0x180258ea0  mov     r8d, 80070057h
0x180258ea6  mov     rcx, rdi
0x180258ea9  call    ?RemoveCommandList@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXW4D3D12_MESSAGE_ID@@JPEBD_K@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(D3D12_MESSAGE_ID,long,char const *,unsigned __int64)
0x180258eae  mov     ecx, [rbx+0E8h]
0x180258eb4  mov     eax, ecx
0x180258eb6  and     eax, 0F000000h
0x180258ebb  cmp     eax, 1000000h
0x180258ec0  jnz     short loc_180258ECB
0x180258ec2  mov     rcx, [rbx+0E0h]
0x180258ec9  jmp     short loc_180258ED1
0x180258ecb  and     ecx, 0FFFFFFh
0x180258ed1  lea     rax, aCountBufferOve; "Count buffer overflow."
0x180258ed8  mov     [rsp+0A8h+var_70], rax
0x180258edd  mov     [rsp+0A8h+var_78], 2E8h
0x180258ee5  mov     [rsp+0A8h+var_80], rcx
0x180258eea  mov     [rsp+0A8h+var_88], r14
0x180258eef  mov     edx, 4
0x180258ef4  mov     r9d, 1
0x180258efa  mov     r8d, edx
0x180258efd  mov     rcx, rdi
0x180258f00  call    ?ValidateSize@?$CCastableCommandList@UID3D12VideoProcessCommandList4@@@@IEAAXIII_K0W4D3D12_MESSAGE_ID@@PEBD@Z; CCastableCommandList<ID3D12VideoProcessCommandList4>::ValidateSize(uint,uint,uint,unsigned __int64,unsigned __int64,D3D12_MESSAGE_ID,char const *)
0x180258f05  jmp     short loc_180258F26
0x180258f07  test    r14, r14
0x180258f0a  jz      short loc_180258F26
0x180258f0c  lea     r9, aIfNoCountBuffe; "If no count buffer is specified, the co"...
0x180258f13  mov     edx, 2E8h
0x180258f18  mov     r8d, 80070057h
0x180258f1e  mov     rcx, rdi
0x180258f21  call    ?RemoveCommandList@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXW4D3D12_MESSAGE_ID@@JPEBD_K@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(D3D12_MESSAGE_ID,long,char const *,unsigned __int64)
0x180258f26  lea     r8, aNodeMaskMismat_2; "Node mask mismatch between command sign"...
0x180258f2d  mov     edx, [rbp+0ECh]
0x180258f33  mov     rcx, rdi
0x180258f36  call    ?ValidateNodeMask@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXIPEBD@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::ValidateNodeMask(uint,char const *)
0x180258f3b  cmp     dword ptr [rdi+118h], 2
0x180258f42  jnz     short loc_180258F63
0x180258f44  test    r12b, r12b
0x180258f47  jnz     short loc_180258F63
0x180258f49  lea     r9, aExecuteindirec_0; "ExecuteIndirect does not support Draw* "...
0x180258f50  mov     edx, 2E8h
0x180258f55  mov     r8d, 80070057h
0x180258f5b  mov     rcx, rdi
0x180258f5e  call    ?RemoveCommandList@?$CCastableCommandList@UID3D12GraphicsCommandList11@@@@QEAAXW4D3D12_MESSAGE_ID@@JPEBD_K@Z; CCastableCommandList<ID3D12GraphicsCommandList11>::RemoveCommandList(D3D12_MESSAGE_ID,long,char const *,unsigned __int64)
0x180258f63  add     rsi, 1A0h
0x180258f6a  test    rbx, rbx
0x180258f6d  jz      short loc_180258F78
0x180258f6f  lea     r8, [rbx+1A0h]
0x180258f76  jmp     short loc_180258F7B
0x180258f78  xor     r8d, r8d
0x180258f7b  lea     rdx, [rsp+0A8h+arg_28]
0x180258f83  mov     rcx, rdi
0x180258f86  call    ?DDIHandle@?$CCommandList@UID3D12GraphicsCommandList11@@@@QEBA?AUD3D12DDI_HCOMMANDLIST@@XZ; CCommandList<ID3D12GraphicsCommandList11>::DDIHandle(void)
0x180258f8b  mov     [rsp+0A8h+var_68], r8
0x180258f90  mov     [rsp+0A8h+var_60], r14
0x180258f95  mov     [rsp+0A8h+var_58], rsi
0x180258f9a  mov     [rsp+0A8h+var_50], r15
0x180258f9f  mov     r11, cs:?g_TableAndSize@@3_KA; unsigned __int64 g_TableAndSize
0x180258fa6  movzx   ecx, r11b
0x180258faa  mov     r10d, 1
0x180258fb0  shl     r10, cl
0x180258fb3  dec     r10
0x180258fb6  mov     rcx, [rdi+170h]
0x180258fbd  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180258fc1  and     r10, rcx
0x180258fc4  and     r11, 0FFFFFFFFFFFF0000h
0x180258fcb  lea     rcx, [rsp+0A8h+var_68]
0x180258fd0  mov     [rsp+0A8h+var_88], rcx
0x180258fd5  lea     r9, [rsp+0A8h+var_58]
0x180258fda  mov     r8d, r13d
0x180258fdd  lea     rdx, [rbp+0F0h]
0x180258fe4  mov     rcx, [rax]
0x180258fe7  call    qword ptr [r10+r11]
0x180258feb  mov     r14, [rbp+0C8h]
0x180258ff2  mov     rbp, [rbp+0D0h]
0x180258ff9  sub     rbp, r14
0x180258ffc  sar     rbp, 4
0x180259000  xor     esi, esi
0x180259002  test    ebp, ebp
0x180259004  jz      loc_1802592CE
0x18025900a  xor     ebx, ebx
0x18025900c  lea     r15, __ImageBase
0x180259013  nop     dword ptr [rax+00h]
0x180259017  nop     word ptr [rax+rax+00000000h]
0x180259020  mov     rdx, rbx
0x180259023  shl     rdx, 4
0x180259027  add     rdx, r14
0x18025902a  mov     eax, [rdx]
0x18025902c  add     eax, 0FFFFFFFDh; switch 9 cases
0x18025902f  cmp     eax, 8
0x180259032  ja      def_180259045; jumptable 0000000180259045 default case, cases 9,10
0x180259038  cdqe
0x18025903a  mov     ecx, ds:(jpt_180259045 - 180000000h)[r15+rax*4]
0x180259042  add     rcx, r15
0x180259045  jmp     rcx; switch jump
0x180259047  mov     edx, [rdx+4]; jumptable 0000000180259045 case 3
0x18025904a  mov     rax, [rdi+110h]
0x180259051  mov     r11, cs:?g_TableAndSize@@3_KA; unsigned __int64 g_TableAndSize
0x180259058  movzx   ecx, r11b
0x18025905c  mov     r10d, 1
0x180259062  shl     r10, cl
0x180259065  dec     r10
0x180259068  mov     rcx, [rdi+170h]
0x18025906f  add     rcx, 170h
0x180259076  and     r10, rcx
0x180259079  and     r11, 0FFFFFFFFFFFF0000h
0x180259080  lea     r9, qword_1802FB520
0x180259087  mov     r8d, 1
0x18025908d  mov     rcx, rax
0x180259090  call    qword ptr [r10+r11]
0x180259094  jmp     def_180259045; jumptable 0000000180259045 default case, cases 9,10
0x180259099  mov     rax, [rdi+110h]; jumptable 0000000180259045 case 4
0x1802590a0  mov     r9, cs:?g_TableAndSize@@3_KA; unsigned __int64 g_TableAndSize
0x1802590a7  movzx   ecx, r9b
0x1802590ab  mov     r8d, 1
0x1802590b1  shl     r8, cl
0x1802590b4  dec     r8
0x1802590b7  mov     rcx, [rdi+170h]
0x1802590be  add     rcx, 168h
0x1802590c5  and     r8, rcx
0x1802590c8  and     r9, 0FFFFFFFFFFFF0000h
0x1802590cf  xor     edx, edx
0x1802590d1  mov     rcx, rax
0x1802590d4  call    qword ptr [r8+r9]
0x1802590d8  jmp     def_180259045; jumptable 0000000180259045 default case, cases 9,10
0x1802590dd  mov     r9d, [rdx+8]; jumptable 0000000180259045 case 5
0x1802590e1  mov     r8d, [rdx+0Ch]
0x1802590e5  mov     rax, [rdi+110h]
0x1802590ec  mov     r10d, 1
0x1802590f2  mov     dword ptr [rsp+0A8h+var_88], r9d
0x1802590f7  mov     edx, [rdx+4]
0x1802590fa  mov     r11, cs:?g_TableAndSize@@3_KA; unsigned __int64 g_TableAndSize
0x180259101  lea     r9, qword_1802FAF60
0x180259108  movzx   ecx, r11b
0x18025910c  shl     r10, cl
0x18025910f  and     r11, 0FFFFFFFFFFFF0000h
0x180259116  dec     r10
0x180259119  mov     rcx, [rdi+170h]
0x180259120  test    r12b, r12b
0x180259123  jz      short loc_180259131
0x180259125  add     rcx, 128h
0x18025912c  jmp     loc_1802592B7
0x180259131  add     rcx, 130h
0x180259138  jmp     loc_1802592B7
0x18025913d  mov     edx, [rdx+4]; jumptable 0000000180259045 case 6
0x180259140  mov     rax, [rdi+110h]
0x180259147  mov     r9d, 1
0x18025914d  xor     r8d, r8d
0x180259150  mov     r10, cs:?g_TableAndSize@@3_KA; unsigned __int64 g_TableAndSize
0x180259157  movzx   ecx, r10b
0x18025915b  shl     r9, cl
0x18025915e  and     r10, 0FFFFFFFFFFFF0000h
0x180259165  dec     r9
0x180259168  mov     rcx, [rdi+170h]
0x18025916f  test    r12b, r12b
0x180259172  jz      short loc_18025918A
0x180259174  add     rcx, 138h
0x18025917b  and     r9, rcx
0x18025917e  mov     rcx, rax
0x180259181  call    qword ptr [r9+r10]
0x180259185  jmp     def_180259045; jumptable 0000000180259045 default case, cases 9,10
0x18025918a  add     rcx, 140h
0x180259191  and     r9, rcx
0x180259194  mov     rcx, rax
0x180259197  call    qword ptr [r9+r10]
0x18025919b  jmp     def_180259045; jumptable 0000000180259045 default case, cases 9,10
0x1802591a0  mov     edx, [rdx+4]; jumptable 0000000180259045 case 7
0x1802591a3  mov     rax, [rdi+110h]
0x1802591aa  mov     r9d, 1
0x1802591b0  xor     r8d, r8d
0x1802591b3  mov     r10, cs:?g_TableAndSize@@3_KA; unsigned __int64 g_TableAndSize
0x1802591ba  movzx   ecx, r10b
0x1802591be  shl     r9, cl
0x1802591c1  and     r10, 0FFFFFFFFFFFF0000h
0x1802591c8  dec     r9
0x1802591cb  mov     rcx, [rdi+170h]
0x1802591d2  test    r12b, r12b
0x1802591d5  jz      short loc_1802591ED
0x1802591d7  add     rcx, 148h
0x1802591de  and     r9, rcx
0x1802591e1  mov     rcx, rax
0x1802591e4  call    qword ptr [r9+r10]
0x1802591e8  jmp     def_180259045; jumptable 0000000180259045 default case, cases 9,10
0x1802591ed  add     rcx, 150h
0x1802591f4  and     r9, rcx
0x1802591f7  mov     rcx, rax
0x1802591fa  call    qword ptr [r9+r10]
0x1802591fe  jmp     def_180259045; jumptable 0000000180259045 default case, cases 9,10
0x180259203  mov     edx, [rdx+4]; jumptable 0000000180259045 case 8
0x180259206  mov     rax, [rdi+110h]
0x18025920d  mov     r9d, 1
0x180259213  xor     r8d, r8d
0x180259216  mov     r10, cs:?g_TableAndSize@@3_KA; unsigned __int64 g_TableAndSize
0x18025921d  movzx   ecx, r10b
0x180259221  shl     r9, cl
  ... truncated ...
```
