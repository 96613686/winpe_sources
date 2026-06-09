# PortpCompleteRequestIrp

- ea: `0x14000b610`
- end: `0x14000baf2`
- name: `PortpCompleteRequestIrp`
- size: `1250`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000b4d0`
- `0x14000b580`

## callees

- `0x14000b610`
- `0x14000baf8`
- `0x14000bbf0`
- `0x140013990`
- `0x140013a40`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000b8e7`
- `ntoskrnl!IoFreeIrp` at `0x14000b8e7`
- `ntoskrnl!IoFreeMdl` at `0x14000b8d0`
- `ntoskrnl!IoFreeMdl` at `0x14000b8d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b915`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b915`
- `ntoskrnl!IoIs32bitProcess` at `0x14000b6dc`
- `ntoskrnl!IoIs32bitProcess` at `0x14000b817`
- `ntoskrnl!IoIs32bitProcess` at `0x14000b6dc`
- `ntoskrnl!IoIs32bitProcess` at `0x14000b817`
- `ntoskrnl!MmUnlockPages` at `0x14000b8c0`
- `ntoskrnl!MmUnlockPages` at `0x14000b8c0`

## pseudocode

```c
void __fastcall PortpCompleteRequestIrp(__int64 a1, char *a2)
{
  IRP *v3; // r15
  __int64 v4; // r12
  IRP *v5; // r14
  unsigned __int64 v6; // r13
  unsigned int Options; // edi
  struct _IRP *v8; // rax
  unsigned __int16 Type; // cx
  unsigned __int64 v10; // rbx
  __int32 v11; // edi
  char v12; // r9
  PVOID Pointer; // xmm8_8
  unsigned int IrpCount; // r8d
  __m128i ThreadListEntry; // xmm6
  __int128 v16; // xmm7
  char v17; // dl
  ULONG Length; // r10d
  int v19; // r8d
  int v20; // r12d
  __int64 v21; // rdx
  struct _IRP *v22; // rax
  struct _MDL *v23; // rcx
  char *v24; // rcx
  unsigned int v25; // [rsp+28h] [rbp-89h]
  CSHORT v26; // [rsp+2Ch] [rbp-85h]
  __int8 MdlAddress; // [rsp+30h] [rbp-81h]
  NTSTATUS Status; // [rsp+34h] [rbp-7Dh]
  __int32 v29; // [rsp+34h] [rbp-7Dh]
  __int8 v30; // [rsp+38h] [rbp-79h]
  struct _IRP *v31; // [rsp+40h] [rbp-71h]
  ULONG_PTR Information; // [rsp+48h] [rbp-69h]
  __m128i v33; // [rsp+50h] [rbp-61h]
  __int128 v34; // [rsp+60h] [rbp-51h]
  _BYTE v35[24]; // [rsp+70h] [rbp-41h]
  ULONG v36; // [rsp+88h] [rbp-29h]
  __int64 v37; // [rsp+90h] [rbp-21h]
  struct _IRP *MasterIrp; // [rsp+118h] [rbp+67h]
  char v39; // [rsp+118h] [rbp+67h]
  char v40; // [rsp+120h] [rbp+6Fh]
  struct _IRP *v41; // [rsp+120h] [rbp+6Fh]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+128h] [rbp+77h]
  __int8 v43; // [rsp+128h] [rbp+77h]
  __int16 v44; // [rsp+130h] [rbp+7Fh]

  v3 = (IRP *)*((_QWORD *)a2 + 1);
  v4 = *((_QWORD *)a2 + 3);
  v5 = (IRP *)*((_QWORD *)a2 + 2);
  Status = v3->IoStatus.Status;
  Information = v3->IoStatus.Information;
  v40 = *a2;
  v37 = v4;
  if ( ((*(_DWORD *)(*(_QWORD *)(a1 + 184) + 24LL) - 315460) & 0xFFFFFFFB) == 0 )
  {
    PortPassThroughExMarshalResultsFromSrbEx(v5);
    v6 = Information;
    v20 = Status;
    goto LABEL_19;
  }
  v6 = 0;
  *(_DWORD *)&v35[20] = 0;
  MasterIrp = v5->AssociatedIrp.MasterIrp;
  Options = v5->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options;
  CurrentStackLocation = v5->Tail.Overlay.CurrentStackLocation;
  if ( IoIs32bitProcess(v5) )
  {
    if ( Options < 0x2C )
    {
      v20 = -1073741811;
      goto LABEL_19;
    }
    v8 = v5->AssociatedIrp.MasterIrp;
    Type = v8->Type;
    v26 = v8->Type;
    if ( v8->Type != 44 )
    {
      v20 = -1073741735;
      goto LABEL_19;
    }
    v10 = *(_QWORD *)&v8->Flags;
    v11 = *(_DWORD *)((char *)&v8->Size + 1);
    v12 = *((_BYTE *)&v8->Size + 5);
    MdlAddress = (__int8)v8->MdlAddress;
    v33.m128i_i8[8] = MdlAddress;
    v44 = *(_WORD *)((char *)&v8->MdlAddress + 1);
    *(__int16 *)((char *)&v33.m128i_i16[4] + 1) = v44;
    *(_OWORD *)&v35[4] = *(_OWORD *)((char *)&v8->AssociatedIrp.SystemBuffer + 4);
    v30 = BYTE3(v8->MdlAddress);
    Pointer = *(PVOID *)&v35[16];
    v33.m128i_i8[11] = v30;
    IrpCount = v8->AssociatedIrp.IrpCount;
    *(_DWORD *)v35 = IrpCount;
    ThreadListEntry = *(__m128i *)v35;
    *(_QWORD *)&v34 = v10;
    *((_QWORD *)&v34 + 1) = HIDWORD(v10);
    v16 = v34;
    v33.m128i_i16[0] = 44;
    *(__int32 *)((char *)v33.m128i_i32 + 3) = v11;
    v31 = (struct _IRP *)HIDWORD(v10);
  }
  else
  {
    if ( Options < 0x38 )
    {
      v20 = -1073741811;
      goto LABEL_19;
    }
    if ( MasterIrp->Type != 56 )
    {
      v20 = -1073741735;
      goto LABEL_19;
    }
    ThreadListEntry = (__m128i)MasterIrp->ThreadListEntry;
    v16 = *(_OWORD *)&MasterIrp->Flags;
    Pointer = MasterIrp->IoStatus.Pointer;
    v30 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&MasterIrp->Type, 11));
    v31 = MasterIrp->AssociatedIrp.MasterIrp;
    v33 = *(__m128i *)&MasterIrp->Type;
    v11 = *(_QWORD *)&MasterIrp->Type >> 24;
    Type = _mm_cvtsi128_si32(*(__m128i *)&MasterIrp->Type);
    v10 = *(_QWORD *)&MasterIrp->Flags;
    v12 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&MasterIrp->Type, 7));
    *(__m128i *)v35 = ThreadListEntry;
    v44 = (unsigned int)MasterIrp->MdlAddress >> 8;
    IrpCount = _mm_cvtsi128_si32(ThreadListEntry);
    MdlAddress = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&MasterIrp->Type, 8));
    v26 = Type;
  }
  v25 = IrpCount;
  if ( !CurrentStackLocation->Parameters.Read.Length )
  {
    v12 = 0;
    IrpCount = 0;
    *(_DWORD *)v35 = 0;
    ThreadListEntry = *(__m128i *)v35;
    v25 = 0;
  }
  v17 = *(_BYTE *)(v4 + 3);
  Length = v5->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
  v43 = *(_BYTE *)(v4 + 4);
  v33.m128i_i8[2] = v43;
  v36 = Length;
  if ( v17 < 0 )
  {
    if ( v12 )
    {
      LOBYTE(v6) = *(_BYTE *)(v4 + 11);
      v39 = v6;
      v33.m128i_i8[7] = v6;
      v24 = (char *)v5->AssociatedIrp.MasterIrp + IrpCount;
      if ( v24 && (_BYTE)v6 )
      {
        memmove(v24, *(const void **)(v4 + 32), *(unsigned __int8 *)(v4 + 11));
        v17 = *(_BYTE *)(v4 + 3);
        Length = v36;
      }
      Type = v26;
      v19 = 0;
    }
    else
    {
      LOBYTE(v6) = *(_BYTE *)(v4 + 11);
      v19 = 0;
      Type = v26;
      v39 = v6;
      v33.m128i_i8[7] = v6;
    }
  }
  else
  {
    v19 = Status;
    v39 = 0;
    v33.m128i_i8[7] = 0;
  }
  v20 = 0;
  if ( (v17 & 0x3F) != 0x12 )
    v20 = v19;
  v21 = *(unsigned int *)(v37 + 16);
  v29 = *(_DWORD *)(v37 + 16);
  v33.m128i_i32[3] = v29;
  if ( (_BYTE)v6 )
  {
    v6 = v25 + (unsigned __int8)v6;
  }
  else
  {
    v6 = Type;
    if ( v20 < 0 && *(_BYTE *)(v37 + 4) )
    {
      v20 = 0;
      v6 = 3;
    }
  }
  if ( !v40 && MdlAddress && (_DWORD)v21 && v31 )
    v6 = (unsigned __int64)v31 + v21;
  if ( v6 >= Length )
    v6 = Length;
  v41 = v5->AssociatedIrp.MasterIrp;
  if ( IoIs32bitProcess(v5) )
  {
    v22 = v5->AssociatedIrp.MasterIrp;
    v22->Type = v26;
    LOBYTE(v22->Size) = v43;
    *((_BYTE *)&v22->Size + 5) = v39;
    LOBYTE(v22->MdlAddress) = MdlAddress;
    *(_WORD *)((char *)&v22->MdlAddress + 1) = v44;
    BYTE3(v22->MdlAddress) = v30;
    HIDWORD(v22->MdlAddress) = v29;
    *(_DWORD *)((char *)&v22->Size + 1) = v11;
    *(_QWORD *)&v22->Flags = v10;
  }
  else
  {
    *(__m128i *)&v41->Type = v33;
    *(_OWORD *)&v41->Flags = v16;
    v41->ThreadListEntry = (LIST_ENTRY)ThreadListEntry;
    v41->IoStatus.Pointer = Pointer;
  }
LABEL_19:
  *(_DWORD *)(*((_QWORD *)a2 + 2) + 48LL) = v20;
  *(_QWORD *)(*((_QWORD *)a2 + 2) + 56LL) = v6;
  v23 = v3->MdlAddress;
  if ( v23 )
  {
    MmUnlockPages(v23);
    IoFreeMdl(v3->MdlAddress);
    v3->MdlAddress = 0;
  }
  IoFreeIrp(v3);
  PortPassThroughFreeSrb(*((PVOID *)a2 + 3));
  (*((void (__fastcall **)(_QWORD, _QWORD))a2 + 4))(*((_QWORD *)a2 + 2), *((_QWORD *)a2 + 5));
  ExFreePoolWithTag(a2, 0x69506C50u);
}

```

## disassembly

```asm
0x14000b610  mov     rax, rsp
0x14000b613  push    rbp
0x14000b614  push    rsi
0x14000b615  push    r15
0x14000b617  lea     rbp, [rax-5Fh]
0x14000b61b  sub     rsp, 0F0h
0x14000b622  mov     [rax-20h], rbx
0x14000b626  mov     rsi, rdx
0x14000b629  mov     [rax-30h], r12
0x14000b62d  mov     [rax-38h], r13
0x14000b631  mov     [rax-40h], r14
0x14000b635  mov     rax, [rcx+0B8h]
0x14000b63c  mov     dword ptr [rbp+57h+var_C8+4], 0
0x14000b643  mov     ecx, [rax+18h]
0x14000b646  sub     ecx, 4D044h
0x14000b64c  test    ecx, 0FFFFFFFBh
0x14000b652  jnz     loc_14000BABB
0x14000b658  mov     cl, 1
0x14000b65a  mov     r15, [rdx+8]
0x14000b65e  movzx   ebx, byte ptr [rdx]
0x14000b661  mov     r12, [rdx+18h]
0x14000b665  mov     r14, [rdx+10h]
0x14000b669  mov     eax, [r15+30h]
0x14000b66d  mov     [rbp+57h+var_D4], eax
0x14000b670  mov     dword ptr [rbp+57h+var_C8], eax
0x14000b673  mov     rax, [r15+38h]
0x14000b677  mov     [rbp+57h+var_C0], rax
0x14000b67b  mov     byte ptr [rbp+57h+arg_8], bl
0x14000b67e  mov     qword ptr [rbp+57h+var_78], r12
0x14000b682  test    cl, cl
0x14000b684  jnz     loc_14000B93C
0x14000b68a  mov     rcx, [r14+18h]
0x14000b68e  xorps   xmm0, xmm0
0x14000b691  mov     [rsp+100h+var_20], rdi
0x14000b699  xor     eax, eax
0x14000b69b  movaps  [rsp+100h+var_58+8], xmm6
0x14000b6a3  xor     r13d, r13d
0x14000b6a6  mov     [rbp+57h+var_88], rax
0x14000b6aa  mov     rax, [r14+0B8h]
0x14000b6b1  mov     [rbp+57h+arg_0], rcx
0x14000b6b5  mov     rcx, r14; Irp
0x14000b6b8  movaps  [rsp+100h+var_68+8], xmm7
0x14000b6c0  movaps  [rsp+100h+var_78+8], xmm8
0x14000b6c9  mov     edi, [rax+10h]
0x14000b6cc  movups  [rbp+57h+var_B8], xmm0
0x14000b6d0  mov     [rbp+57h+arg_10], rax
0x14000b6d4  movups  [rbp+57h+var_A8], xmm0
0x14000b6d8  movups  [rbp+57h+var_98], xmm0
0x14000b6dc  call    cs:__imp_IoIs32bitProcess
0x14000b6e3  nop     dword ptr [rax+rax+00h]
0x14000b6e8  test    al, al
0x14000b6ea  jz      loc_14000B9A4
0x14000b6f0  cmp     edi, 2Ch ; ','
0x14000b6f3  jb      loc_14000BA2E
0x14000b6f9  mov     rax, [r14+18h]
0x14000b6fd  movzx   ecx, word ptr [rax]
0x14000b700  mov     [rsp+24h], ecx
0x14000b704  cmp     cx, 2Ch ; ','
0x14000b708  jnz     loc_14000BA96
0x14000b70e  movzx   r8d, byte ptr [rax+8]
0x14000b713  mov     rbx, [rax+10h]
0x14000b717  movups  xmm0, xmmword ptr [rax+1Ch]
0x14000b71b  mov     edi, [rax+3]
0x14000b71e  mov     rdx, rbx
0x14000b721  movzx   r9d, byte ptr [rax+7]
0x14000b726  mov     [rsp+28h], r8d
0x14000b72b  mov     byte ptr [rbp+57h+var_B8+8], r8b
0x14000b72f  movzx   r8d, word ptr [rax+9]
0x14000b734  mov     [rbp+57h+arg_18], r8w
0x14000b739  mov     word ptr [rbp+57h+var_B8+9], r8w
0x14000b73e  movzx   r8d, byte ptr [rax+0Bh]
0x14000b743  shr     rdx, 20h
0x14000b747  movups  [rbp+57h+var_98+4], xmm0
0x14000b74b  mov     dword ptr [rbp+57h+var_D0], r8d
0x14000b74f  movsd   xmm8, [rbp+57h+var_88]
0x14000b755  mov     byte ptr [rbp+57h+var_B8+0Bh], r8b
0x14000b759  mov     r8d, [rax+18h]
0x14000b75d  mov     dword ptr [rbp+57h+var_98], r8d
0x14000b761  movups  xmm6, [rbp+57h+var_98]
0x14000b765  mov     qword ptr [rbp+57h+var_A8], rbx
0x14000b769  mov     qword ptr [rbp+57h+var_A8+8], rdx
0x14000b76d  movups  xmm7, [rbp+57h+var_A8]
0x14000b771  mov     word ptr [rbp+57h+var_B8], cx
0x14000b775  mov     dword ptr [rbp+57h+var_B8+3], edi
0x14000b778  mov     [rbp+57h+var_C8], rdx
0x14000b77c  mov     rax, [rbp+57h+arg_10]
0x14000b780  mov     [rsp+100h+var_E0], r8d
0x14000b785  cmp     [rax+8], r13d
0x14000b789  jz      loc_14000BAC2
0x14000b78f  mov     rax, [r14+0B8h]
0x14000b796  movzx   edx, byte ptr [r12+3]
0x14000b79c  mov     r10d, [rax+8]
0x14000b7a0  movzx   eax, byte ptr [r12+4]
0x14000b7a6  mov     byte ptr [rbp+57h+arg_10], al
0x14000b7a9  mov     byte ptr [rbp+57h+var_B8+2], al
0x14000b7ac  mov     [rbp+57h+var_80], r10d
0x14000b7b0  test    dl, dl
0x14000b7b2  js      loc_14000B95C
0x14000b7b8  mov     r8d, [rbp+57h+var_D4]
0x14000b7bc  mov     byte ptr [rbp+57h+arg_0], r13b
0x14000b7c0  mov     byte ptr [rbp+57h+var_B8+7], r13b
0x14000b7c4  movzx   eax, dl
0x14000b7c7  xor     r12d, r12d
0x14000b7ca  and     eax, 0FFFFFF3Fh
0x14000b7cf  cmp     al, 12h
0x14000b7d1  mov     rax, qword ptr [rbp+57h+var_78]
0x14000b7d5  cmovnz  r12d, r8d
0x14000b7d9  mov     edx, [rax+10h]
0x14000b7dc  mov     [rbp+57h+var_D4], edx
0x14000b7df  mov     dword ptr [rbp+57h+var_B8+0Ch], edx
0x14000b7e2  test    r13b, r13b
0x14000b7e5  jnz     loc_14000B92E
0x14000b7eb  movzx   r13d, cx
0x14000b7ef  test    r12d, r12d
0x14000b7f2  js      loc_14000BADA
0x14000b7f8  cmp     byte ptr [rbp+57h+arg_8], 0
0x14000b7fc  jz      loc_14000BA57
0x14000b802  mov     eax, r10d
0x14000b805  mov     rcx, r14; Irp
0x14000b808  cmp     r13, rax
0x14000b80b  cmovnb  r13, rax
0x14000b80f  mov     rax, [r14+18h]
0x14000b813  mov     [rbp+57h+arg_8], rax
0x14000b817  call    cs:__imp_IoIs32bitProcess
0x14000b81e  nop     dword ptr [rax+rax+00h]
0x14000b823  test    al, al
0x14000b825  jz      loc_14000BA39
0x14000b82b  mov     rax, [r14+18h]
0x14000b82f  mov     ecx, [rsp+24h]
0x14000b833  mov     [rax], cx
0x14000b836  movzx   ecx, byte ptr [rbp+57h+arg_10]
0x14000b83a  mov     [rax+2], cl
0x14000b83d  movzx   ecx, byte ptr [rbp+57h+arg_0]
0x14000b841  mov     [rax+7], cl
0x14000b844  mov     ecx, [rsp+28h]
0x14000b848  mov     [rax+8], cl
0x14000b84b  movzx   ecx, [rbp+57h+arg_18]
0x14000b84f  mov     [rax+9], cx
0x14000b853  mov     ecx, dword ptr [rbp+57h+var_D0]
0x14000b856  mov     [rax+0Bh], cl
0x14000b859  mov     ecx, [rbp+57h+var_D4]
0x14000b85c  mov     [rax+0Ch], ecx
0x14000b85f  mov     [rax+3], edi
0x14000b862  mov     [rax+10h], rbx
0x14000b866  movaps  xmm7, [rsp+100h+var_68+8]
0x14000b86e  movaps  xmm6, [rsp+100h+var_58+8]
0x14000b876  mov     rdi, [rsp+100h+var_20]
0x14000b87e  movaps  xmm8, [rsp+100h+var_78+8]
0x14000b887  mov     rax, [rsi+10h]
0x14000b88b  mov     r14, [rsp+100h+var_38]
0x14000b893  mov     rbx, [rsp+0E8h]
0x14000b89b  mov     [rax+30h], r12d
0x14000b89f  mov     rax, [rsi+10h]
0x14000b8a3  mov     r12, [rsp+100h+var_28]
0x14000b8ab  mov     [rax+38h], r13
0x14000b8af  mov     rcx, [r15+8]; MemoryDescriptorList
0x14000b8b3  mov     r13, [rsp+100h+var_30]
0x14000b8bb  test    rcx, rcx
0x14000b8be  jz      short loc_14000B8E4
0x14000b8c0  call    cs:__imp_MmUnlockPages
0x14000b8c7  nop     dword ptr [rax+rax+00h]
0x14000b8cc  mov     rcx, [r15+8]; Mdl
0x14000b8d0  call    cs:__imp_IoFreeMdl
0x14000b8d7  nop     dword ptr [rax+rax+00h]
0x14000b8dc  mov     qword ptr [r15+8], 0
0x14000b8e4  mov     rcx, r15; Irp
0x14000b8e7  call    cs:__imp_IoFreeIrp
0x14000b8ee  nop     dword ptr [rax+rax+00h]
0x14000b8f3  mov     rcx, [rsi+18h]; P
0x14000b8f7  call    PortPassThroughFreeSrb
0x14000b8fc  mov     rax, [rsi+20h]
0x14000b900  mov     rdx, [rsi+28h]
0x14000b904  mov     rcx, [rsi+10h]
0x14000b908  call    _guard_dispatch_icall
0x14000b90d  mov     edx, 69506C50h; Tag
0x14000b912  mov     rcx, rsi; P
0x14000b915  call    cs:__imp_ExFreePoolWithTag
0x14000b91c  nop     dword ptr [rax+rax+00h]
0x14000b921  add     rsp, 0F0h
0x14000b928  pop     r15
0x14000b92a  pop     rsi
0x14000b92b  pop     rbp
0x14000b92c  retn
0x14000b92e  movzx   r13d, r13b
0x14000b932  add     r13d, [rsp+100h+var_E0]
0x14000b937  jmp     loc_14000B7F8
0x14000b93c  lea     r9, [rbp+57h+var_C8]
0x14000b940  movzx   r8d, bl
0x14000b944  mov     rdx, r12
0x14000b947  mov     rcx, r14; Irp
0x14000b94a  call    PortPassThroughExMarshalResultsFromSrbEx
0x14000b94f  mov     r13, [rbp+57h+var_C0]
0x14000b953  mov     r12d, dword ptr [rbp+57h+var_C8]
0x14000b957  jmp     loc_14000B887
0x14000b95c  test    r9b, r9b
0x14000b95f  jz      loc_14000BAA1
0x14000b965  movzx   r13d, byte ptr [r12+0Bh]
0x14000b96b  mov     ecx, r8d
0x14000b96e  mov     byte ptr [rbp+57h+arg_0], r13b
0x14000b972  mov     byte ptr [rbp+57h+var_B8+7], r13b
0x14000b976  add     rcx, [r14+18h]; void *
0x14000b97a  jz      short loc_14000B998
0x14000b97c  test    r13b, r13b
0x14000b97f  jz      short loc_14000B998
0x14000b981  mov     rdx, [r12+20h]; Src
0x14000b986  mov     r8d, r13d; Size
0x14000b989  call    memmove
0x14000b98e  movzx   edx, byte ptr [r12+3]
0x14000b994  mov     r10d, [rbp+57h+var_80]
0x14000b998  mov     ecx, [rsp+24h]
0x14000b99c  xor     r8d, r8d
0x14000b99f  jmp     loc_14000B7C4
0x14000b9a4  cmp     edi, 38h ; '8'
0x14000b9a7  jb      loc_14000BA80
0x14000b9ad  mov     rax, [rbp+57h+arg_0]
0x14000b9b1  cmp     word ptr [rax], 38h ; '8'
0x14000b9b5  jnz     loc_14000BA8B
0x14000b9bb  movups  xmm2, xmmword ptr [rax]
0x14000b9be  movq    xmm0, qword ptr [rax+18h]
0x14000b9c3  movups  xmm6, xmmword ptr [rax+20h]
0x14000b9c7  movups  xmm7, xmmword ptr [rax+10h]
0x14000b9cb  movsd   xmm8, qword ptr [rax+30h]
0x14000b9d1  movdqa  xmm1, xmm2
0x14000b9d5  psrldq  xmm1, 0Bh
0x14000b9da  movd    dword ptr [rbp+57h+var_D0], xmm1
0x14000b9df  movdqa  xmm1, xmm2
0x14000b9e3  movq    [rbp+57h+var_C8], xmm0
0x14000b9e8  movdqa  xmm0, xmm2
0x14000b9ec  movups  [rbp+57h+var_B8], xmm2
0x14000b9f0  movzx   eax, word ptr [rbp+57h+var_B8+9]
0x14000b9f4  mov     edi, dword ptr [rbp+57h+var_B8+3]
0x14000b9f7  movd    ecx, xmm2
0x14000b9fb  psrldq  xmm1, 7
0x14000ba00  psrldq  xmm0, 8
0x14000ba05  movups  [rbp+57h+var_A8], xmm7
0x14000ba09  mov     rbx, qword ptr [rbp+57h+var_A8]
0x14000ba0d  movd    r9d, xmm1
0x14000ba12  movups  [rbp+57h+var_98], xmm6
0x14000ba16  mov     [rbp+57h+arg_18], ax
0x14000ba1a  movd    r8d, xmm6
0x14000ba1f  movd    dword ptr [rsp+28h], xmm0
0x14000ba25  mov     [rsp+24h], ecx
0x14000ba29  jmp     loc_14000B77C
0x14000ba2e  mov     r12d, 0C000000Dh
0x14000ba34  jmp     loc_14000B866
0x14000ba39  mov     rax, [rbp+57h+arg_8]
0x14000ba3d  movups  xmm0, [rbp+57h+var_B8]
0x14000ba41  movups  xmmword ptr [rax], xmm0
0x14000ba44  movups  xmmword ptr [rax+10h], xmm7
0x14000ba48  movups  xmmword ptr [rax+20h], xmm6
0x14000ba4c  movsd   qword ptr [rax+30h], xmm8
0x14000ba52  jmp     loc_14000B866
0x14000ba57  cmp     byte ptr [rsp+28h], 0
0x14000ba5c  jz      loc_14000B802
0x14000ba62  test    edx, edx
0x14000ba64  jz      loc_14000B802
0x14000ba6a  mov     rax, [rbp+57h+var_C8]
0x14000ba6e  test    rax, rax
0x14000ba71  jz      loc_14000B802
0x14000ba77  lea     r13, [rax+rdx]
0x14000ba7b  jmp     loc_14000B802
0x14000ba80  mov     r12d, 0C000000Dh
0x14000ba86  jmp     loc_14000B866
0x14000ba8b  mov     r12d, 0C0000059h
0x14000ba91  jmp     loc_14000B866
0x14000ba96  mov     r12d, 0C0000059h
0x14000ba9c  jmp     loc_14000B866
0x14000baa1  movzx   r13d, byte ptr [r12+0Bh]
0x14000baa7  xor     r8d, r8d
0x14000baaa  mov     ecx, [rsp+24h]
0x14000baae  mov     byte ptr [rbp+57h+arg_0], r13b
0x14000bab2  mov     byte ptr [rbp+57h+var_B8+7], r13b
0x14000bab6  jmp     loc_14000B7C4
0x14000babb  xor     cl, cl
0x14000babd  jmp     loc_14000B65A
0x14000bac2  xor     r9b, r9b
0x14000bac5  xor     r8d, r8d
0x14000bac8  mov     dword ptr [rbp+57h+var_98], r8d
0x14000bacc  movups  xmm6, [rbp+57h+var_98]
0x14000bad0  mov     [rsp+100h+var_E0], r8d
0x14000bad5  jmp     loc_14000B78F
0x14000bada  cmp     byte ptr [rax+4], 0
0x14000bade  jz      loc_14000B7F8
0x14000bae4  xor     r12d, r12d
0x14000bae7  mov     r13d, 3
0x14000baed  jmp     loc_14000B7F8
```
