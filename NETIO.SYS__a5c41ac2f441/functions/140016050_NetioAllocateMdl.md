# NetioAllocateMdl

- ea: `0x140016050`
- end: `0x14001624f`
- name: `NetioAllocateMdl`
- size: `511`
- prototype: `_QWORD *__fastcall(PULONG BufferSize)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14003c940`

## callees

- `0x140016050`
- `0x140016258`
- `0x140017680`
- `0x1400176d0`
- `0x14001771c`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x1400161ea`
- `ntoskrnl!ExAllocatePool3` at `0x1400161ea`
- `ntoskrnl!MmSizeOfMdl` at `0x14001607f`
- `ntoskrnl!MmSizeOfMdl` at `0x14001607f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400161a1`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400161a1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140016111`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140016111`

## pseudocode

```c
_QWORD *__fastcall NetioAllocateMdl(PULONG BufferSize)
{
  __int64 v1; // rdi
  int v3; // r14d
  unsigned int v4; // esi
  unsigned int v5; // ebp
  _QWORD *Pool3; // rax
  int LockArray_high; // r13d
  _BYTE *v8; // rbp
  int v9; // esi
  unsigned __int64 v10; // rbx
  _DWORD *v11; // rax
  _QWORD *v12; // rbx
  ULONG v13; // esi
  _QWORD v15[11]; // [rsp+30h] [rbp-58h] BYREF

  v1 = *BufferSize;
  if ( (unsigned int)v1 <= 0xB0 )
  {
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    v8 = NetioProtocolHeader2Pool;
    v9 = 96;
    if ( (unsigned int)v1 > 0x60 )
      v9 = 176;
    else
      v8 = NetioProtocolHeader1Pool;
    v10 = (unsigned __int64)(unsigned int)(LockArray_high + 1) << 7;
    if ( !v8[v10 + 176] )
      PplpLazyInitializeLookasideList(v8, &v8[v10 + 64]);
    v11 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)&v8[v10 + 64]);
    v12 = v11;
    if ( v11 )
    {
      v11[10] = *((_DWORD *)v8 + 4);
      v13 = v9 - (-(int)v1 & 7);
      *((_WORD *)v11 + 6) = LockArray_high;
      *(_QWORD *)v11 = 0;
      *((_WORD *)v11 + 5) |= 0x1000u;
      v11[10] = v13;
      *BufferSize = v13;
    }
    return v12;
  }
  v3 = HIDWORD(KeGetPcr()[1].LockArray);
  v4 = (MmSizeOfMdl((PVOID)0xFFF, (unsigned int)v1) + 7) & 0xFFFFFFF8;
  v5 = v4 + v1 + 8;
  if ( v5 >= v4 )
  {
    if ( v5 >= 0x708 )
    {
      v15[1] = 0;
      v15[0] = 1;
      Pool3 = (_QWORD *)ExAllocatePool3(66, v5, 1718968910, v15, 1);
    }
    else if ( (unsigned int)Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageInline() )
    {
      Pool3 = (_QWORD *)PplAllocateFromLookasideListProcessor(NetioNetBufferDataPool, (unsigned __int16)v3);
    }
    else
    {
      Pool3 = (_QWORD *)PplAllocateFromLookasideList(NetioNetBufferDataPool);
    }
    v12 = Pool3;
    if ( Pool3 )
    {
      v12 = Pool3 + 1;
      *Pool3 = 0;
      if ( v5 < 0x708 )
      {
        *(_BYTE *)Pool3 = 1;
        if ( (unsigned int)Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageInline() )
          *((_WORD *)v12 + 6) = v3;
      }
      *v12 = 0;
      *((_WORD *)v12 + 5) = 0;
      *((_DWORD *)v12 + 10) = v1;
      v12[4] = ((unsigned __int64)v12 + v4) & 0xFFFFFFFFFFFFF000uLL;
      *((_DWORD *)v12 + 11) = ((_WORD)v12 + (_WORD)v4) & 0xFFF;
      *((_WORD *)v12 + 4) = 8 * (((v1 + (unsigned __int64)(((_WORD)v12 + (_WORD)v4) & 0xFFF) + 4095) >> 12) + 6);
      MmBuildMdlForNonPagedPool((PMDL)v12);
    }
    return v12;
  }
  return 0;
}

```

## disassembly

```asm
0x140016050  push    rbx
0x140016052  push    rbp
0x140016053  push    rsi
0x140016054  push    rdi
0x140016055  push    r12
0x140016057  push    r13
0x140016059  push    r14
0x14001605b  push    r15
0x14001605d  sub     rsp, 48h
0x140016061  mov     edi, [rcx]
0x140016063  mov     r14, rcx
0x140016066  mov     ecx, 0B0h
0x14001606b  cmp     edi, ecx
0x14001606d  jbe     short loc_1400160CF
0x14001606f  mov     r14d, gs:1A4h
0x140016078  mov     edx, edi; Length
0x14001607a  mov     ecx, 0FFFh; Base
0x14001607f  call    cs:__imp_MmSizeOfMdl
0x140016086  nop     dword ptr [rax+rax+00h]
0x14001608b  lea     ebp, [rdi+8]
0x14001608e  lea     esi, [rax+7]
0x140016091  and     esi, 0FFFFFFF8h
0x140016094  add     ebp, esi
0x140016096  cmp     ebp, esi
0x140016098  jb      loc_14001622D
0x14001609e  xor     r15d, r15d
0x1400160a1  cmp     ebp, 708h
0x1400160a7  jnb     loc_1400161C2
0x1400160ad  call    Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageInline
0x1400160b2  mov     rcx, cs:NetioNetBufferDataPool
0x1400160b9  test    eax, eax
0x1400160bb  jz      loc_140016234
0x1400160c1  movzx   edx, r14w
0x1400160c5  call    PplAllocateFromLookasideListProcessor
0x1400160ca  jmp     loc_1400161F6
0x1400160cf  mov     r13d, gs:1A4h
0x1400160d8  cmp     edi, 60h ; '`'
0x1400160db  mov     rbp, cs:NetioProtocolHeader2Pool
0x1400160e2  mov     esi, 60h ; '`'
0x1400160e7  cmovbe  rbp, cs:NetioProtocolHeader1Pool
0x1400160ef  cmova   esi, ecx
0x1400160f2  lea     ebx, [r13+1]
0x1400160f6  shl     rbx, 7
0x1400160fa  movzx   eax, byte ptr [rbx+rbp+0B0h]
0x140016102  test    al, al
0x140016104  jz      loc_14001623B
0x14001610a  lea     rcx, [rbx+40h]
0x14001610e  add     rcx, rbp; Lookaside
0x140016111  call    cs:__imp_ExAllocateFromLookasideListEx
0x140016118  nop     dword ptr [rax+rax+00h]
0x14001611d  mov     rbx, rax
0x140016120  test    rax, rax
0x140016123  jz      loc_1400161AD
0x140016129  mov     eax, [rbp+10h]
0x14001612c  neg     edi
0x14001612e  mov     [rbx+28h], eax
0x140016131  and     edi, 7
0x140016134  sub     esi, edi
0x140016136  mov     [rbx+0Ch], r13w
0x14001613b  xor     r15d, r15d
0x14001613e  mov     eax, 1000h
0x140016143  mov     [rbx], r15
0x140016146  or      [rbx+0Ah], ax
0x14001614a  mov     [rbx+28h], esi
0x14001614d  mov     [r14], esi
0x140016150  jmp     short loc_1400161AD
0x140016152  mov     edx, esi
0x140016154  add     rdx, rbx
0x140016157  mov     [rbx], r15
0x14001615a  mov     r8d, edx
0x14001615d  mov     [rbx+0Ah], r15w
0x140016162  mov     ecx, r8d
0x140016165  mov     [rbx+28h], edi
0x140016168  and     ecx, 0FFFh
0x14001616e  and     rdx, 0FFFFFFFFFFFFF000h
0x140016175  add     rcx, 0FFFh
0x14001617c  mov     [rbx+20h], rdx
0x140016180  add     rcx, rdi
0x140016183  and     r8d, 0FFFh
0x14001618a  shr     rcx, 0Ch
0x14001618e  add     cx, 6
0x140016192  mov     [rbx+2Ch], r8d
0x140016196  shl     cx, 3
0x14001619a  mov     [rbx+8], cx
0x14001619e  mov     rcx, rbx; MemoryDescriptorList
0x1400161a1  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400161a8  nop     dword ptr [rax+rax+00h]
0x1400161ad  mov     rax, rbx
0x1400161b0  add     rsp, 48h
0x1400161b4  pop     r15
0x1400161b6  pop     r14
0x1400161b8  pop     r13
0x1400161ba  pop     r12
0x1400161bc  pop     rdi
0x1400161bd  pop     rsi
0x1400161be  pop     rbp
0x1400161bf  pop     rbx
0x1400161c0  retn
0x1400161c2  mov     edx, ebp
0x1400161c4  lea     r9, [rsp+88h+var_58]
0x1400161c9  mov     ecx, 42h ; 'B'
0x1400161ce  mov     [rsp+88h+var_50], r15
0x1400161d3  mov     r8d, 6675624Eh
0x1400161d9  mov     [rsp+88h+var_58], 1
0x1400161e2  mov     [rsp+88h+var_68], 1
0x1400161ea  call    cs:__imp_ExAllocatePool3
0x1400161f1  nop     dword ptr [rax+rax+00h]
0x1400161f6  mov     rbx, rax
0x1400161f9  test    rax, rax
0x1400161fc  jz      short loc_1400161AD
0x1400161fe  xor     ecx, ecx
0x140016200  add     rbx, 8
0x140016204  mov     [rax], rcx
0x140016207  cmp     ebp, 708h
0x14001620d  jnb     loc_140016152
0x140016213  mov     byte ptr [rax], 1
0x140016216  call    Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageInline
0x14001621b  test    eax, eax
0x14001621d  jz      loc_140016152
0x140016223  mov     [rbx+0Ch], r14w
0x140016228  jmp     loc_140016152
0x14001622d  xor     eax, eax
0x14001622f  jmp     loc_1400161B0
0x140016234  call    PplAllocateFromLookasideList
0x140016239  jmp     short loc_1400161F6
0x14001623b  lea     rdx, [rbx+40h]
0x14001623f  mov     rcx, rbp
0x140016242  add     rdx, rbp
0x140016245  call    PplpLazyInitializeLookasideList
0x14001624a  jmp     loc_14001610A
```
