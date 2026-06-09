# RootHub_DetectLinkErrorState

- ea: `0x140022b1c`
- end: `0x140022cd4`
- name: `RootHub_DetectLinkErrorState`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400214dc`

## callees

- `0x140010d40`
- `0x1400110e0`
- `0x14001ac48`
- `0x14001f830`
- `0x1400218a0`
- `0x1400219b0`
- `0x140022b1c`
- `0x140022cdc`
- `0x140022ddc`
- `0x1400599b0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140022ba5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022ba5`

## pseudocode

```c
__int64 __fastcall RootHub_DetectLinkErrorState(__int64 a1)
{
  unsigned int v1; // r13d
  char v2; // r12
  unsigned int v3; // esi
  __int64 result; // rax
  __int64 v6; // r14
  __int64 v7; // r15
  __int64 v8; // rbp
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rcx
  unsigned int *v12; // r15
  int Ulong; // eax
  __int64 v14; // rcx
  char v15; // [rsp+80h] [rbp+8h]
  int v16; // [rsp+88h] [rbp+10h] BYREF
  __int64 v17; // [rsp+90h] [rbp+18h]
  __int64 v18; // [rsp+98h] [rbp+20h]

  v1 = *(_DWORD *)(a1 + 16);
  v2 = 0;
  v16 = 0;
  v3 = 1;
  result = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 88LL);
  v18 = result;
  if ( v1 )
  {
    do
    {
      v6 = *(_QWORD *)(a1 + 48);
      v7 = v3 - 1;
      v8 = 120 * v7;
      if ( *(_BYTE *)(v6 + 120 * v7 + 13) != 2 )
      {
        v17 = *(_QWORD *)(a1 + 40);
        v15 = 0;
        if ( KeGetCurrentIrql() == 2 )
        {
          v9 = *(_QWORD *)(a1 + 8);
          if ( *(_BYTE *)(v9 + 1041) )
          {
            Controller_LowerAndTrackIrql(v9);
            v15 = 1;
          }
        }
        v10 = *(_QWORD *)(a1 + 48);
        DynamicLock_Acquire(*(_QWORD *)(v10 + v8 + 24));
        v11 = v18;
        v12 = (unsigned int *)(v17 + 16 * v7);
        *(_BYTE *)(v10 + v8 + 32) = v15;
        Ulong = XilRegister_ReadUlong(v11, v12);
        v14 = *(_QWORD *)(a1 + 48);
        v16 = Ulong;
        LOBYTE(v10) = *(_BYTE *)(v14 + v8 + 32);
        *(_BYTE *)(v14 + v8 + 32) = 0;
        DynamicLock_Release(*(_QWORD *)(v14 + v8 + 24));
        if ( (_BYTE)v10 )
          Controller_RaiseAndTrackIrql(*(_QWORD *)(a1 + 8));
        if ( RootHub_DetectPortInComplianceMode(a1, v3, &v16)
          || (result = RootHub_DetectPortInInactiveState(a1, v3, &v16), (_BYTE)result) )
        {
          v2 = 1;
          result = (unsigned int)_InterlockedExchange((volatile __int32 *)(v6 + v8 + 100), 1);
          *(_BYTE *)(v6 + v8 + 104) = 1;
        }
      }
      ++v3;
    }
    while ( v3 <= v1 );
    if ( v2 == 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          *(_QWORD *)(*(_QWORD *)(a1 + 8) + 72LL),
          4,
          11,
          268,
          (__int64)WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids);
      return ((__int64 (__fastcall *)(__int64, _QWORD))qword_14006CCF0)(UcxDriverGlobals, *(_QWORD *)a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140022b1c  mov     rax, rsp
0x140022b1f  push    rbx
0x140022b20  push    rbp
0x140022b21  push    rsi
0x140022b22  push    rdi
0x140022b23  push    r12
0x140022b25  push    r13
0x140022b27  push    r14
0x140022b29  push    r15
0x140022b2b  sub     rsp, 38h
0x140022b2f  mov     r13d, [rcx+10h]
0x140022b33  xor     r12b, r12b
0x140022b36  mov     dword ptr [rax+10h], 0
0x140022b3d  mov     esi, 1
0x140022b42  mov     rax, [rcx+8]
0x140022b46  mov     rdi, rcx
0x140022b49  mov     rax, [rax+58h]
0x140022b4d  mov     [rsp+78h+arg_18], rax
0x140022b55  cmp     r13d, esi
0x140022b58  jb      short loc_140022B7F
0x140022b5a  mov     r14, [rdi+30h]
0x140022b5e  lea     r15d, [rsi-1]
0x140022b62  imul    rbp, r15, 78h ; 'x'
0x140022b66  cmp     byte ptr [r14+rbp+0Dh], 2
0x140022b6c  jnz     short loc_140022B91
0x140022b6e  inc     esi
0x140022b70  cmp     esi, r13d
0x140022b73  jbe     short loc_140022B5A
0x140022b75  cmp     r12b, 1
0x140022b79  jz      loc_140022C82
0x140022b7f  add     rsp, 38h
0x140022b83  pop     r15
0x140022b85  pop     r14
0x140022b87  pop     r13
0x140022b89  pop     r12
0x140022b8b  pop     rdi
0x140022b8c  pop     rsi
0x140022b8d  pop     rbp
0x140022b8e  pop     rbx
0x140022b8f  retn
0x140022b91  mov     rax, [rdi+28h]
0x140022b95  mov     [rsp+78h+arg_10], rax
0x140022b9d  mov     [rsp+78h+arg_0], 0
0x140022ba5  call    cs:__imp_KeGetCurrentIrql
0x140022bac  nop     dword ptr [rax+rax+00h]
0x140022bb1  cmp     al, 2
0x140022bb3  jnz     short loc_140022BC6
0x140022bb5  mov     rcx, [rdi+8]
0x140022bb9  cmp     byte ptr [rcx+411h], 0
0x140022bc0  jnz     loc_140022C65
0x140022bc6  mov     rbx, [rdi+30h]
0x140022bca  mov     rcx, [rbx+rbp+18h]
0x140022bcf  call    DynamicLock_Acquire
0x140022bd4  mov     al, [rsp+78h+arg_0]
0x140022bdb  mov     rcx, [rsp+78h+arg_18]
0x140022be3  shl     r15, 4
0x140022be7  add     r15, [rsp+78h+arg_10]
0x140022bef  mov     rdx, r15
0x140022bf2  mov     [rbx+rbp+20h], al
0x140022bf6  call    XilRegister_ReadUlong
0x140022bfb  mov     rcx, [rdi+30h]
0x140022bff  mov     [rsp+78h+arg_8], eax
0x140022c06  mov     bl, [rcx+rbp+20h]
0x140022c0a  mov     byte ptr [rcx+rbp+20h], 0
0x140022c0f  mov     rcx, [rcx+rbp+18h]
0x140022c14  call    DynamicLock_Release
0x140022c19  test    bl, bl
0x140022c1b  jnz     short loc_140022C77
0x140022c1d  lea     r8, [rsp+78h+arg_8]
0x140022c25  mov     edx, esi
0x140022c27  mov     rcx, rdi
0x140022c2a  call    RootHub_DetectPortInComplianceMode
0x140022c2f  test    al, al
0x140022c31  jnz     short loc_140022C4D
0x140022c33  lea     r8, [rsp+78h+arg_8]
0x140022c3b  mov     edx, esi
0x140022c3d  mov     rcx, rdi
0x140022c40  call    RootHub_DetectPortInInactiveState
0x140022c45  test    al, al
0x140022c47  jz      loc_140022B6E
0x140022c4d  mov     eax, 1
0x140022c52  mov     r12b, 1
0x140022c55  xchg    eax, [r14+rbp+64h]
0x140022c5a  mov     byte ptr [r14+rbp+68h], 1
0x140022c60  jmp     loc_140022B6E
0x140022c65  call    Controller_LowerAndTrackIrql
0x140022c6a  mov     [rsp+78h+arg_0], 1
0x140022c72  jmp     loc_140022BC6
0x140022c77  mov     rcx, [rdi+8]
0x140022c7b  call    Controller_RaiseAndTrackIrql
0x140022c80  jmp     short loc_140022C1D
0x140022c82  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140022c89  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140022c90  jz      short loc_140022CB9
0x140022c92  mov     rcx, [rdi+8]
0x140022c96  lea     rax, WPP_ae3f3dc960bf3cde3d0f419b97453dd4_Traceguids
0x140022c9d  mov     r9d, 10Ch
0x140022ca3  mov     [rsp+78h+var_58], rax
0x140022ca8  mov     r8d, 0Bh
0x140022cae  mov     dl, 4
0x140022cb0  mov     rcx, [rcx+48h]
0x140022cb4  call    WPP_RECORDER_SF_
0x140022cb9  mov     rax, cs:qword_14006CCF0
0x140022cc0  mov     rdx, [rdi]
0x140022cc3  mov     rcx, cs:UcxDriverGlobals
0x140022cca  call    _guard_dispatch_icall
0x140022ccf  jmp     loc_140022B7F
```
