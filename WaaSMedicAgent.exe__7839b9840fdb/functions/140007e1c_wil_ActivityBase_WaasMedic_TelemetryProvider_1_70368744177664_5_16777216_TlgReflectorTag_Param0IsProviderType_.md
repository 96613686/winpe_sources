# wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)

- ea: `0x140007e1c`
- end: `0x140007f33`
- name: `?Destroy@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `279`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x140007c7c`
- `0x140007f3c`
- `0x1400093c0`
- `0x14000a8f0`

## callees

- `0x140002dd8`
- `0x14000369c`
- `0x140007220`
- `0x140007ab0`
- `0x140007e1c`
- `0x14000830c`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007eb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007eb0`

## pseudocode

```c
void __fastcall wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rcx
  char v3; // si
  char *v4; // rdi
  _DWORD *v5; // rcx
  int v6; // eax
  int v7; // edx
  const struct wil::FailureInfo *v8; // rdx
  PSRWLOCK SRWLock[2]; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v10[160]; // [rsp+30h] [rbp-A8h] BYREF

  SRWLock[1] = (PSRWLOCK)-2LL;
  if ( !a1[35] )
    goto LABEL_13;
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    SRWLock);
  v2 = (volatile signed __int32 *)a1[35];
  if ( v2 && *v2 == 1 )
  {
    v3 = 1;
  }
  else
  {
    v3 = 0;
    if ( v2 )
    {
      if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
      {
        v4 = (char *)a1[35];
        if ( v4 )
        {
          wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(v4 + 8);
          operator delete(v4);
        }
      }
      a1[35] = 0;
    }
  }
  if ( SRWLock[0] )
    ReleaseSRWLockExclusive(SRWLock[0]);
  if ( v3 )
  {
LABEL_13:
    v5 = (_DWORD *)a1[34];
    if ( *v5 == 1 )
    {
      v6 = -2147024322;
      if ( (int)v5[22] < 0 )
        v6 = v5[22];
      v7 = v5[62];
      if ( v7 < 1 )
      {
        memset_0(v10, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v10, v8);
      }
      if ( (int)v5[18] >= 0 )
        v5[18] = v6;
      v5[62] = v7 - 1;
      (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
    }
  }
}

```

## disassembly

```asm
0x140007e1c  mov     rax, rsp
0x140007e1f  push    rdi
0x140007e20  sub     rsp, 0D0h
0x140007e27  mov     [rsp+0D8h+var_B0], 0FFFFFFFFFFFFFFFEh
0x140007e30  mov     [rax+10h], rbx
0x140007e34  mov     [rax+18h], rsi
0x140007e38  mov     rbx, rcx
0x140007e3b  cmp     qword ptr [rcx+118h], 0
0x140007e43  jz      short loc_140007EBB
0x140007e45  lea     rdx, [rsp+0D8h+SRWLock]
0x140007e4a  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140007e4f  mov     rcx, [rbx+118h]
0x140007e56  test    rcx, rcx
0x140007e59  jz      short loc_140007E65
0x140007e5b  cmp     dword ptr [rcx], 1
0x140007e5e  jnz     short loc_140007E65
0x140007e60  mov     sil, 1
0x140007e63  jmp     short loc_140007EA6
0x140007e65  xor     sil, sil
0x140007e68  test    rcx, rcx
0x140007e6b  jz      short loc_140007EA6
0x140007e6d  or      eax, 0FFFFFFFFh
0x140007e70  lock xadd [rcx], eax
0x140007e74  cmp     eax, 1
0x140007e77  jnz     short loc_140007E9B
0x140007e79  mov     rdi, [rbx+118h]
0x140007e80  test    rdi, rdi
0x140007e83  jz      short loc_140007E9B
0x140007e85  lea     rcx, [rdi+8]
0x140007e89  call    ??1?$ActivityData@VTelemetryProvider@WaasMedic@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WaasMedic::TelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)
0x140007e8e  mov     edx, 110h
0x140007e93  mov     rcx, rdi; Block
0x140007e96  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007e9b  mov     qword ptr [rbx+118h], 0
0x140007ea6  mov     rcx, [rsp+0D8h+SRWLock]; SRWLock
0x140007eab  test    rcx, rcx
0x140007eae  jz      short loc_140007EB6
0x140007eb0  call    cs:__imp_ReleaseSRWLockExclusive
0x140007eb6  test    sil, sil
0x140007eb9  jz      short loc_140007F01
0x140007ebb  mov     rcx, [rbx+110h]
0x140007ec2  cmp     dword ptr [rcx], 1
0x140007ec5  jnz     short loc_140007F01
0x140007ec7  mov     eax, 8007023Eh
0x140007ecc  cmp     dword ptr [rcx+58h], 0
0x140007ed0  cmovl   eax, [rcx+58h]
0x140007ed4  mov     edx, [rcx+0F8h]
0x140007eda  cmp     edx, 1
0x140007edd  jl      short loc_140007F16
0x140007edf  cmp     dword ptr [rcx+48h], 0
0x140007ee3  jl      short loc_140007EE8
0x140007ee5  mov     [rcx+48h], eax
0x140007ee8  lea     eax, [rdx-1]
0x140007eeb  mov     [rcx+0F8h], eax
0x140007ef1  mov     rax, [rbx]
0x140007ef4  mov     rcx, rbx
0x140007ef7  mov     rax, [rax+8]
0x140007efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f00  nop
0x140007f01  lea     r11, [rsp+0D8h+var_8]
0x140007f09  mov     rbx, [r11+18h]
0x140007f0d  mov     rsi, [r11+20h]
0x140007f11  mov     rsp, r11
0x140007f14  pop     rdi
0x140007f15  retn
0x140007f16  xor     edx, edx; Val
0x140007f18  mov     r8d, 98h; Size
0x140007f1e  lea     rcx, [rsp+0D8h+var_A8]; void *
0x140007f23  call    memset_0
0x140007f28  lea     rcx, [rsp+0D8h+var_A8]; this
0x140007f2d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
