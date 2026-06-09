# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140005298`
- end: `0x1400053ab`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004d38`
- `0x140005524`

## callees

- `0x140005298`
- `0x14000540c`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r14d
  signed __int32 v5; // edi
  __int16 CurrentFeatureEnabledState; // bx
  int v8; // ebp
  unsigned int v9; // esi
  signed __int32 v10; // eax
  int v12; // [rsp+50h] [rbp+8h] BYREF
  __int64 v13; // [rsp+58h] [rbp+10h]

  v3 = 0;
  v12 = 0;
  v13 = a2;
  v5 = a2;
  if ( WPP_MAIN_CB.Reserved )
    v3 = ((__int64 (*)(void))WPP_MAIN_CB.Reserved)();
  CurrentFeatureEnabledState = wil_details_GetCurrentFeatureEnabledState(a3, &v12);
  if ( *(_BYTE *)(a3 + 28) )
    v8 = v12;
  else
    v8 = v3 != 0 ? v12 : 0;
  while ( 1 )
  {
    LODWORD(v13) = v5;
    v9 = v5;
    if ( v8 )
    {
      LODWORD(v13) = v5;
      if ( (v5 & 2) == 0 )
      {
        v9 = CurrentFeatureEnabledState & 0x9C1 | v5 & 0xFFFFF63E | 2;
        LODWORD(v13) = v9;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v9 = v9 & 0xFFFFFBFF | CurrentFeatureEnabledState & 0x400 | 4;
      LODWORD(v13) = v9;
    }
    v10 = _InterlockedCompareExchange(a1, v9, v5);
    if ( v5 == v10 )
      break;
    v5 = v10;
  }
  if ( (v5 & 4) == 0 && WPP_MAIN_CB.DeviceObjectExtension )
    ((void (__fastcall *)(volatile signed __int32 *, _QWORD, _QWORD))WPP_MAIN_CB.DeviceObjectExtension)(
      a1,
      *(unsigned __int8 *)(a3 + 28),
      v3);
  if ( !v8 )
    LODWORD(v13) = v9 & 0xFFFFF63E | CurrentFeatureEnabledState & 0x9C1;
  return v13;
}

```

## disassembly

```asm
0x140005298  mov     [rsp+arg_10], rbx
0x14000529d  mov     [rsp+arg_18], rbp
0x1400052a2  push    rsi
0x1400052a3  push    rdi
0x1400052a4  push    r12
0x1400052a6  push    r14
0x1400052a8  push    r15
0x1400052aa  sub     rsp, 20h
0x1400052ae  mov     rax, cs:WPP_MAIN_CB.Reserved
0x1400052b5  xor     r14d, r14d
0x1400052b8  mov     [rsp+48h+arg_0], r14d
0x1400052bd  mov     r15, r8
0x1400052c0  mov     [rsp+48h+arg_8], rdx
0x1400052c5  mov     rdi, rdx
0x1400052c8  mov     r12, rcx
0x1400052cb  test    rax, rax
0x1400052ce  jz      short loc_1400052D8
0x1400052d0  call    _guard_dispatch_icall
0x1400052d5  mov     r14d, eax
0x1400052d8  lea     rdx, [rsp+48h+arg_0]
0x1400052dd  mov     rcx, r15
0x1400052e0  call    wil_details_GetCurrentFeatureEnabledState
0x1400052e5  cmp     byte ptr [r15+1Ch], 0
0x1400052ea  mov     rbx, rax
0x1400052ed  jnz     short loc_1400052FC
0x1400052ef  mov     ecx, r14d
0x1400052f2  neg     ecx
0x1400052f4  sbb     ebp, ebp
0x1400052f6  and     ebp, [rsp+48h+arg_0]
0x1400052fa  jmp     short loc_140005300
0x1400052fc  mov     ebp, [rsp+48h+arg_0]
0x140005300  mov     dword ptr [rsp+48h+arg_8], edi
0x140005304  mov     esi, edi
0x140005306  test    ebp, ebp
0x140005308  jz      short loc_14000532A
0x14000530a  mov     dword ptr [rsp+48h+arg_8], edi
0x14000530e  test    dil, 2
0x140005312  jnz     short loc_14000532A
0x140005314  and     esi, 0FFFFF63Eh
0x14000531a  mov     eax, ebx
0x14000531c  and     eax, 9C1h
0x140005321  or      esi, eax
0x140005323  or      esi, 2
0x140005326  mov     dword ptr [rsp+48h+arg_8], esi
0x14000532a  mov     edx, edi
0x14000532c  and     edx, 4
0x14000532f  jnz     short loc_14000534A
0x140005331  mov     eax, esi
0x140005333  mov     ecx, ebx
0x140005335  and     ecx, 400h
0x14000533b  btr     eax, 0Ah
0x14000533f  mov     esi, ecx
0x140005341  or      esi, eax
0x140005343  or      esi, 4
0x140005346  mov     dword ptr [rsp+48h+arg_8], esi
0x14000534a  mov     eax, edi
0x14000534c  lock cmpxchg [r12], esi
0x140005352  jz      short loc_140005358
0x140005354  mov     edi, eax
0x140005356  jmp     short loc_140005300
0x140005358  test    edx, edx
0x14000535a  jnz     short loc_140005378
0x14000535c  mov     rax, cs:WPP_MAIN_CB.DeviceObjectExtension
0x140005363  test    rax, rax
0x140005366  jz      short loc_140005378
0x140005368  movzx   edx, byte ptr [r15+1Ch]
0x14000536d  mov     r8d, r14d
0x140005370  mov     rcx, r12
0x140005373  call    _guard_dispatch_icall
0x140005378  test    ebp, ebp
0x14000537a  jnz     short loc_14000538E
0x14000537c  and     ebx, 9C1h
0x140005382  and     esi, 0FFFFF63Eh
0x140005388  or      ebx, esi
0x14000538a  mov     dword ptr [rsp+48h+arg_8], ebx
0x14000538e  mov     rax, [rsp+48h+arg_8]
0x140005393  mov     rbx, [rsp+48h+arg_10]
0x140005398  mov     rbp, [rsp+48h+arg_18]
0x14000539d  add     rsp, 20h
0x1400053a1  pop     r15
0x1400053a3  pop     r14
0x1400053a5  pop     r12
0x1400053a7  pop     rdi
0x1400053a8  pop     rsi
0x1400053a9  retn
```
