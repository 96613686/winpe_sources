# CBufferSourceManager::CompleteCopyBuffer_(CTStickyVal<int> *)

- ea: `0x180028e18`
- end: `0x180028f9e`
- name: `?CompleteCopyBuffer_@CBufferSourceManager@@AEAAJPEAV?$CTStickyVal@H@@@Z`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180028dc4`

## callees

- `0x180019a60`
- `0x180028e18`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CBufferSourceManager::CompleteCopyBuffer_(__int64 a1, __int64 a2)
{
  _QWORD *v2; // r14
  _DWORD *v3; // r15
  __int64 (__fastcall **v4)(__int64, __int64); // r8
  __int64 v5; // r13
  int v6; // r9d
  int *v7; // rbp
  int v10; // edi
  __int64 *v11; // rcx
  int v12; // r9d
  __int64 v13; // rdx
  __int64 v14; // rax
  int v15; // eax
  __int64 result; // rax
  unsigned int v17; // [rsp+A0h] [rbp+8h] BYREF

  v2 = (_QWORD *)(a1 + 88);
  v3 = (_DWORD *)(a1 + 28);
  v4 = *(__int64 (__fastcall ***)(__int64, __int64))a1;
  v5 = a1 + 40;
  v6 = *(_DWORD *)(a1 + 28);
  v7 = (int *)(a1 + 72);
  v17 = *(_DWORD *)(a1 + 104) - *(_DWORD *)(a1 + 88);
  if ( ((unsigned int (__fastcall *)(__int64, _QWORD, __int64, unsigned int *, __int64, __int64, __int64, __int64))v4[2])(
         a1,
         0,
         a1 + 88,
         &v17,
         a1 + 72,
         a1 + 28,
         (a1 + 32) & -(__int64)(v6 != 0),
         (a1 + 40) & -(__int64)(v6 != 0)) )
  {
    Mpeg2DemuxAttributes::CAttributeList::Reset((Mpeg2DemuxAttributes::CAttributeList *)(a1 + 120));
    v10 = (**(__int64 (__fastcall ***)(__int64, __int64))a1)(a1, a1 + 120);
    if ( v10 >= 0 )
    {
      v11 = *(__int64 **)(a1 + 8);
      v12 = *v7;
      v13 = *(_QWORD *)(a1 + 80);
      v14 = *v11;
      if ( *v3 )
        v15 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, _QWORD, int, __int64, __int64, __int64, __int64))(v14 + 32))(
                v11,
                v13,
                *v2,
                v17,
                v12,
                a1 + 32,
                v5,
                a2,
                a1 + 120);
      else
        v15 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, _QWORD, int, __int64, __int64))(v14 + 40))(
                v11,
                v13,
                *v2,
                v17,
                v12,
                a2,
                a1 + 120);
      v10 = v15;
      if ( !v15 )
        *(_QWORD *)(a1 + 112) += (int)v17;
    }
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 8LL))(a1, (unsigned int)v10);
  }
  else
  {
    v10 = 0;
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 8) + 48LL))(
    *(_QWORD *)(a1 + 8),
    *(_QWORD *)(a1 + 80),
    *v2,
    *(unsigned int *)(a1 + 96));
  result = (unsigned int)v10;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *v2 = 0;
  *v3 = 0;
  *(_DWORD *)(a1 + 96) = 0;
  return result;
}

```

## disassembly

```asm
0x180028e18  mov     r11, rsp
0x180028e1b  push    rbx
0x180028e1c  push    rbp
0x180028e1d  push    rsi
0x180028e1e  push    rdi
0x180028e1f  push    r12
0x180028e21  push    r13
0x180028e23  push    r14
0x180028e25  push    r15
0x180028e27  sub     rsp, 58h
0x180028e2b  mov     eax, [rcx+68h]
0x180028e2e  lea     r14, [rcx+58h]
0x180028e32  sub     eax, [r14]
0x180028e35  lea     r15, [rcx+1Ch]
0x180028e39  mov     r8, [rcx]
0x180028e3c  lea     r13, [rcx+28h]
0x180028e40  mov     r9d, [r15]
0x180028e43  lea     rbp, [rcx+48h]
0x180028e47  mov     [r11+8], eax
0x180028e4b  lea     r10, [rcx+20h]
0x180028e4f  mov     eax, r9d
0x180028e52  mov     r12, rdx
0x180028e55  neg     eax
0x180028e57  mov     rbx, rcx
0x180028e5a  mov     rax, [r8+10h]
0x180028e5e  mov     r8, r14
0x180028e61  sbb     rdx, rdx
0x180028e64  and     rdx, r13
0x180028e67  mov     [r11-60h], rdx
0x180028e6b  neg     r9d
0x180028e6e  lea     r9, [r11+8]
0x180028e72  sbb     rcx, rcx
0x180028e75  xor     edx, edx
0x180028e77  and     rcx, r10
0x180028e7a  mov     [r11-68h], rcx
0x180028e7e  mov     rcx, rbx
0x180028e81  mov     [r11-70h], r15
0x180028e85  mov     [r11-78h], rbp
0x180028e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e8e  test    eax, eax
0x180028e90  jz      loc_180028F49
0x180028e96  lea     rsi, [rbx+78h]
0x180028e9a  mov     rcx, rsi; this
0x180028e9d  call    ?Reset@CAttributeList@Mpeg2DemuxAttributes@@QEAAXXZ; Mpeg2DemuxAttributes::CAttributeList::Reset(void)
0x180028ea2  mov     rax, [rbx]
0x180028ea5  mov     rdx, rsi
0x180028ea8  mov     rcx, rbx
0x180028eab  mov     rax, [rax]
0x180028eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eb3  mov     edi, eax
0x180028eb5  test    eax, eax
0x180028eb7  js      short loc_180028F36
0x180028eb9  cmp     dword ptr [r15], 0
0x180028ebd  mov     rcx, [rbx+8]
0x180028ec1  mov     r9d, [rbp+0]
0x180028ec5  mov     rdx, [rbx+50h]
0x180028ec9  mov     rax, [rcx]
0x180028ecc  jnz     short loc_180028EF3
0x180028ece  mov     r8, [r14]
0x180028ed1  mov     rax, [rax+28h]
0x180028ed5  mov     [rsp+98h+var_68], rsi
0x180028eda  mov     [rsp+98h+var_70], r12
0x180028edf  mov     [rsp+98h+var_78], r9d
0x180028ee4  mov     r9d, [rsp+98h+arg_0]
0x180028eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ef1  jmp     short loc_180028F24
0x180028ef3  mov     rax, [rax+20h]
0x180028ef7  lea     r8, [rbx+20h]
0x180028efb  mov     [rsp+98h+var_58], rsi
0x180028f00  mov     [rsp+98h+var_60], r12
0x180028f05  mov     [rsp+98h+var_68], r13
0x180028f0a  mov     [rsp+98h+var_70], r8
0x180028f0f  mov     r8, [r14]
0x180028f12  mov     [rsp+98h+var_78], r9d
0x180028f17  mov     r9d, [rsp+98h+arg_0]
0x180028f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f24  mov     edi, eax
0x180028f26  test    eax, eax
0x180028f28  jnz     short loc_180028F36
0x180028f2a  movsxd  rax, [rsp+98h+arg_0]
0x180028f32  add     [rbx+70h], rax
0x180028f36  mov     rax, [rbx]
0x180028f39  mov     edx, edi
0x180028f3b  mov     rcx, rbx
0x180028f3e  mov     rax, [rax+8]
0x180028f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f47  jmp     short loc_180028F4B
0x180028f49  xor     edi, edi
0x180028f4b  mov     rcx, [rbx+8]
0x180028f4f  mov     r9d, [rbx+60h]
0x180028f53  mov     r8, [r14]
0x180028f56  mov     rdx, [rbx+50h]
0x180028f5a  mov     rax, [rcx]
0x180028f5d  mov     rax, [rax+30h]
0x180028f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f66  mov     eax, edi
0x180028f68  mov     qword ptr [rbx+50h], 0
0x180028f70  mov     qword ptr [rbx+68h], 0
0x180028f78  mov     qword ptr [r14], 0
0x180028f7f  mov     dword ptr [r15], 0
0x180028f86  mov     dword ptr [rbx+60h], 0
0x180028f8d  add     rsp, 58h
0x180028f91  pop     r15
0x180028f93  pop     r14
0x180028f95  pop     r13
0x180028f97  pop     r12
0x180028f99  pop     rdi
0x180028f9a  pop     rsi
0x180028f9b  pop     rbp
0x180028f9c  pop     rbx
0x180028f9d  retn
```
