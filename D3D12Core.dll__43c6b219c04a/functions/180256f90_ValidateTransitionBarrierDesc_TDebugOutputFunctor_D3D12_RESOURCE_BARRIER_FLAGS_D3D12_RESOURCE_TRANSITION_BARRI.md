# ValidateTransitionBarrierDesc(TDebugOutputFunctor &,D3D12_RESOURCE_BARRIER_FLAGS,D3D12_RESOURCE_TRANSITION_BARRIER const *,D3D12_COMMAND_LIST_TYPE,DeviceValidationInfo const &)

- ea: `0x180256f90`
- end: `0x180257260`
- name: `?ValidateTransitionBarrierDesc@@YAJAEAUTDebugOutputFunctor@@W4D3D12_RESOURCE_BARRIER_FLAGS@@PEBUD3D12_RESOURCE_TRANSITION_BARRIER@@W4D3D12_COMMAND_LIST_TYPE@@AEBUDeviceValidationInfo@@@Z`
- size: `720`
- prototype: `__int64 __usercall@<rax>(struct TDebugOutputFunctor *@<rcx>, enum D3D12_RESOURCE_BARRIER_FLAGS@<edx>, const struct D3D12_RESOURCE_TRANSITION_BARRIER *@<r8>, enum D3D12_COMMAND_LIST_TYPE@<r9d>, const struct DeviceValidationInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180246e08`

## callees

- `0x18002ef50`
- `0x1800641b4`
- `0x180256f90`

## string_xrefs

- `0x1802570bf`: `D3D12_RESOURCE_STATES has invalid flags (0x%x) for 3D command list.`
- `0x180257177`: `D3D12_RESOURCE_STATES has invalid flags (0x%x) for compute command list.`
- `0x1802571c8`: `D3D12_RESOURCE_STATES has invalid flags (0x%x) for copy command list.`
- `0x1802571da`: `D3D12_RESOURCE_STATES has invalid flags (0x%x) for video process command list.`
- `0x1802571ec`: `D3D12_RESOURCE_STATES has invalid flags (0x%x) for video decode command list.`
- `0x1802571fe`: `D3D12_RESOURCE_STATES has invalid flags (0x%x) for video encode command list.`

## pseudocode

```c
__int64 __fastcall ValidateTransitionBarrierDesc(
        struct TDebugOutputFunctor *a1,
        enum D3D12_RESOURCE_BARRIER_FLAGS a2,
        const struct D3D12_RESOURCE_TRANSITION_BARRIER *a3,
        enum D3D12_COMMAND_LIST_TYPE a4,
        const struct DeviceValidationInfo *a5)
{
  ID3D12Resource *pResource; // rax
  char v6; // r10
  enum D3D12_HEAP_TYPE WriteToSubresource_low; // esi
  ID3D12Resource_vtbl *v10; // rcx
  enum D3D12_RESOURCE_FLAGS v11; // ebx
  unsigned int Subresource; // edx
  enum D3D12_RESOURCE_STATES StateAfter; // ecx
  enum D3D12_RESOURCE_STATES StateBefore; // edx
  unsigned int v15; // r8d
  enum D3D12_RESOURCE_DIMENSION v16; // r14d
  __int64 v17; // rdi
  enum D3D12_RESOURCE_STATES v18; // ebp
  const char *v19; // r8
  int v20; // r9d
  const char *v22; // r8
  __int64 v23; // rdx
  unsigned int v24; // [rsp+40h] [rbp-48h]
  enum D3D12_RESOURCE_STATES v25[2]; // [rsp+48h] [rbp-40h]

  pResource = a3->pResource;
  v6 = a2;
  if ( !a3->pResource )
  {
    TDebugOutputFunctor::operator()(a1, 520, "NULL pointer specified.");
    return 2147942487LL;
  }
  WriteToSubresource_low = D3D12_HEAP_TYPE_DEFAULT;
  if ( (unsigned __int8)(LOBYTE(pResource[49].__vftable) - 3) > 1u )
  {
    v10 = pResource[50].__vftable;
    if ( v10 )
    {
      if ( LOBYTE(v10[1].WriteToSubresource) == 4 )
        WriteToSubresource_low = D3D12_HEAP_TYPE_CUSTOM;
      else
        WriteToSubresource_low = SLOBYTE(v10[1].WriteToSubresource);
    }
  }
  v11 = (__int64)pResource[32].__vftable & 0xFFFFFEFF;
  if ( (BYTE4(pResource[32].__vftable) & 4) == 0 )
    v11 = (enum D3D12_RESOURCE_FLAGS)pResource[32].__vftable;
  Subresource = a3->Subresource;
  if ( Subresource != -1 && Subresource >= (HIDWORD(pResource[30].__vftable) & 0xFFFFFFu) )
  {
    v22 = "Invalid subresource index.";
    v23 = 521;
LABEL_25:
    TDebugOutputFunctor::operator()(a1, v23, v22);
    return 2147942487LL;
  }
  StateAfter = a3->StateAfter;
  StateBefore = a3->StateBefore;
  if ( StateBefore == StateAfter )
  {
    TDebugOutputFunctor::operator()(a1, 525, "Before and after states must be different.");
    return 2147942487LL;
  }
  if ( StateBefore == D3D12_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE )
  {
    v22 = "Resources in state D3D12_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE cannot be transitioned to another state.";
    goto LABEL_36;
  }
  if ( StateAfter == D3D12_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE )
  {
    v22 = "Resources cannot be transitioned into state D3D12_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE.";
LABEL_36:
    v23 = 526;
    goto LABEL_25;
  }
  if ( (v6 & 2) == 0 )
  {
    v15 = (unsigned int)pResource[31].__vftable;
    v16 = (16 * LODWORD(pResource[29].__vftable)) >> 28;
    v17 = 0;
    v24 = v15;
    v25[0] = StateBefore;
    v25[1] = StateAfter;
    while ( (unsigned int)v17 < 2 )
    {
      v18 = v25[v17];
      if ( (int)ValidateResourceStateCore(a1, v18, v16, v15, v11, a5, WriteToSubresource_low) < 0 )
        return 2147942487LL;
      if ( a4 == D3D12_COMMAND_LIST_TYPE_BUNDLE )
      {
LABEL_17:
        v19 = "D3D12_RESOURCE_STATES has invalid flags (0x%x) for 3D command list.";
        v20 = 29376511;
        if ( !*((_DWORD *)a5 + 202) )
          v20 = 16793599;
      }
      else
      {
        v20 = 0;
        v19 = 0;
        switch ( a4 )
        {
          case D3D12_COMMAND_LIST_TYPE_DIRECT:
            goto LABEL_17;
          case D3D12_COMMAND_LIST_TYPE_COMPUTE:
            v20 = 3657;
            v19 = "D3D12_RESOURCE_STATES has invalid flags (0x%x) for compute command list.";
            break;
          case D3D12_COMMAND_LIST_TYPE_COPY:
            v20 = 3072;
            v19 = "D3D12_RESOURCE_STATES has invalid flags (0x%x) for copy command list.";
            break;
          case D3D12_COMMAND_LIST_TYPE_VIDEO_DECODE:
            v20 = 198144;
            v19 = "D3D12_RESOURCE_STATES has invalid flags (0x%x) for video decode command list.";
            break;
          case D3D12_COMMAND_LIST_TYPE_VIDEO_PROCESS:
            v20 = 787968;
            v19 = "D3D12_RESOURCE_STATES has invalid flags (0x%x) for video process command list.";
            break;
          case D3D12_COMMAND_LIST_TYPE_VIDEO_ENCODE:
            v20 = 10487296;
            v19 = "D3D12_RESOURCE_STATES has invalid flags (0x%x) for video encode command list.";
            break;
          default:
            break;
        }
      }
      if ( (v20 & v18) != v18 )
      {
        TDebugOutputFunctor::operator()(a1, 537, v19, v18 & (unsigned int)~v20);
        return 2147942487LL;
      }
      v15 = v24;
      v17 = (unsigned int)(v17 + 1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180256f90  push    r12
0x180256f92  push    r13
0x180256f94  push    r15
0x180256f96  sub     rsp, 70h
0x180256f9a  mov     rax, [r8]
0x180256f9d  mov     r10d, edx
0x180256fa0  mov     r15, [rsp+88h+arg_20]
0x180256fa8  mov     r13, rcx
0x180256fab  movsxd  r12, r9d
0x180256fae  test    rax, rax
0x180256fb1  jz      loc_1802571A1
0x180256fb7  movzx   ecx, byte ptr [rax+188h]
0x180256fbe  mov     [rsp+88h+arg_8], rbx
0x180256fc6  sub     cl, 3
0x180256fc9  mov     [rsp+88h+var_28], rsi
0x180256fce  mov     esi, 1
0x180256fd3  cmp     cl, sil
0x180256fd6  jbe     short loc_180256FF6
0x180256fd8  mov     rcx, [rax+190h]
0x180256fdf  test    rcx, rcx
0x180256fe2  jz      short loc_180256FF6
0x180256fe4  movsx   edx, byte ptr [rcx+0D8h]
0x180256feb  cmp     dl, 4
0x180256fee  jz      loc_180257143
0x180256ff4  mov     esi, edx
0x180256ff6  mov     edx, [rax+100h]
0x180256ffc  mov     ebx, edx
0x180256ffe  btr     ebx, 8
0x180257002  test    byte ptr [rax+104h], 4
0x180257009  cmovz   ebx, edx
0x18025700c  mov     edx, [r8+8]
0x180257010  cmp     edx, 0FFFFFFFFh
0x180257013  jnz     loc_180257114
0x180257019  mov     ecx, [r8+10h]
0x18025701d  mov     edx, [r8+0Ch]
0x180257021  cmp     edx, ecx
0x180257023  jz      loc_180257183
0x180257029  cmp     edx, 400000h
0x18025702f  jz      loc_18025721B
0x180257035  cmp     ecx, 400000h
0x18025703b  jz      loc_18025720A
0x180257041  mov     [rsp+88h+var_20], rbp
0x180257046  mov     [rsp+88h+var_30], rdi
0x18025704b  mov     [rsp+88h+var_38], r14
0x180257050  test    r10b, 2
0x180257054  jnz     loc_1802570EB
0x18025705a  mov     r14d, [rax+0E8h]
0x180257061  mov     r8d, [rax+0F8h]
0x180257068  shl     r14d, 4
0x18025706c  sar     r14d, 1Ch
0x180257070  xor     edi, edi
0x180257072  mov     [rsp+88h+var_48], r8d
0x180257077  mov     [rsp+88h+var_40], edx
0x18025707b  mov     [rsp+88h+var_3C], ecx
0x18025707f  cmp     edi, 2
0x180257082  jnb     short loc_1802570EB
0x180257084  mov     ebp, [rsp+rdi*4+88h+var_40]
0x180257088  mov     r9d, r8d; unsigned int
0x18025708b  mov     [rsp+88h+var_58], esi; enum D3D12_HEAP_TYPE
0x18025708f  mov     r8d, r14d; enum D3D12_RESOURCE_DIMENSION
0x180257092  mov     [rsp+88h+var_60], r15; struct DeviceValidationInfo *
0x180257097  mov     edx, ebp; enum D3D12_RESOURCE_STATES
0x180257099  mov     rcx, r13; struct TDebugOutputFunctor *
0x18025709c  mov     [rsp+88h+var_68], ebx; enum D3D12_RESOURCE_FLAGS
0x1802570a0  call    ?ValidateResourceStateCore@@YAJAEAUTDebugOutputFunctor@@W4D3D12_RESOURCE_STATES@@W4D3D12_RESOURCE_DIMENSION@@IW4D3D12_RESOURCE_FLAGS@@AEBUDeviceValidationInfo@@W4D3D12_HEAP_TYPE@@@Z; ValidateResourceStateCore(TDebugOutputFunctor &,D3D12_RESOURCE_STATES,D3D12_RESOURCE_DIMENSION,uint,D3D12_RESOURCE_FLAGS,DeviceValidationInfo const &,D3D12_HEAP_TYPE)
0x1802570a5  test    eax, eax
0x1802570a7  js      loc_180257237
0x1802570ad  cmp     r12d, 1
0x1802570b1  jnz     loc_18025714D
0x1802570b7  cmp     dword ptr [r15+328h], 0; jumptable 000000018025716F case 0
0x1802570bf  lea     r8, aD3d12ResourceS_1; "D3D12_RESOURCE_STATES has invalid flags"...
0x1802570c6  mov     r9d, 1C03FFFh
0x1802570cc  mov     eax, 1003FFFh
0x1802570d1  cmovz   r9d, eax
0x1802570d5  mov     eax, ebp; jumptable 000000018025716F default case, case 1
0x1802570d7  and     eax, r9d
0x1802570da  cmp     eax, ebp
0x1802570dc  jnz     loc_180257224
0x1802570e2  mov     r8d, [rsp+88h+var_48]
0x1802570e7  inc     edi
0x1802570e9  jmp     short loc_18025707F
0x1802570eb  xor     eax, eax
0x1802570ed  mov     rdi, [rsp+88h+var_30]
0x1802570f2  mov     rbp, [rsp+88h+var_20]
0x1802570f7  mov     r14, [rsp+88h+var_38]
0x1802570fc  mov     rbx, [rsp+88h+arg_8]
0x180257104  mov     rsi, [rsp+88h+var_28]
0x180257109  add     rsp, 70h
0x18025710d  pop     r15
0x18025710f  pop     r13
0x180257111  pop     r12
0x180257113  retn
0x180257114  mov     ecx, [rax+0F4h]
0x18025711a  and     ecx, 0FFFFFFh
0x180257120  cmp     edx, ecx
0x180257122  jb      loc_180257019
0x180257128  lea     r8, aInvalidSubreso; "Invalid subresource index."
0x18025712f  mov     edx, 209h
0x180257134  mov     rcx, r13
0x180257137  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18025713c  mov     eax, 80070057h
0x180257141  jmp     short loc_1802570FC
0x180257143  mov     esi, 4
0x180257148  jmp     loc_180256FF6
0x18025714d  xor     r9d, r9d
0x180257150  xor     r8d, r8d
0x180257153  cmp     r12d, 6; switch 7 cases
0x180257157  ja      def_18025716F; jumptable 000000018025716F default case, case 1
0x18025715d  lea     rdx, __ImageBase
0x180257164  mov     ecx, ds:(jpt_18025716F - 180000000h)[rdx+r12*4]
0x18025716c  add     rcx, rdx
0x18025716f  jmp     rcx; switch jump
0x180257171  mov     r9d, 0E49h; jumptable 000000018025716F case 2
0x180257177  lea     r8, aD3d12ResourceS_30; "D3D12_RESOURCE_STATES has invalid flags"...
0x18025717e  jmp     def_18025716F; jumptable 000000018025716F default case, case 1
0x180257183  lea     r8, aBeforeAndAfter; "Before and after states must be differe"...
0x18025718a  mov     edx, 20Dh
0x18025718f  mov     rcx, r13
0x180257192  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180257197  mov     eax, 80070057h
0x18025719c  jmp     loc_1802570FC
0x1802571a1  lea     r8, aNullPointerSpe; "NULL pointer specified."
0x1802571a8  mov     edx, 208h
0x1802571ad  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802571b2  mov     eax, 80070057h
0x1802571b7  add     rsp, 70h
0x1802571bb  pop     r15
0x1802571bd  pop     r13
0x1802571bf  pop     r12
0x1802571c1  retn
0x1802571c2  mov     r9d, 0C00h; jumptable 000000018025716F case 3
0x1802571c8  lea     r8, aD3d12ResourceS_6; "D3D12_RESOURCE_STATES has invalid flags"...
0x1802571cf  jmp     def_18025716F; jumptable 000000018025716F default case, case 1
0x1802571d4  mov     r9d, 0C0600h; jumptable 000000018025716F case 5
0x1802571da  lea     r8, aD3d12ResourceS_7; "D3D12_RESOURCE_STATES has invalid flags"...
0x1802571e1  jmp     def_18025716F; jumptable 000000018025716F default case, case 1
0x1802571e6  mov     r9d, 30600h; jumptable 000000018025716F case 4
0x1802571ec  lea     r8, aD3d12ResourceS_28; "D3D12_RESOURCE_STATES has invalid flags"...
0x1802571f3  jmp     def_18025716F; jumptable 000000018025716F default case, case 1
0x1802571f8  mov     r9d, 0A00600h; jumptable 000000018025716F case 6
0x1802571fe  lea     r8, aD3d12ResourceS_10; "D3D12_RESOURCE_STATES has invalid flags"...
0x180257205  jmp     def_18025716F; jumptable 000000018025716F default case, case 1
0x18025720a  lea     r8, aResourcesCanno; "Resources cannot be transitioned into s"...
0x180257211  mov     edx, 20Eh
0x180257216  jmp     loc_180257134
0x18025721b  lea     r8, aResourcesInSta; "Resources in state D3D12_RESOURCE_STATE"...
0x180257222  jmp     short loc_180257211
0x180257224  not     r9d
0x180257227  mov     edx, 219h
0x18025722c  and     r9d, ebp
0x18025722f  mov     rcx, r13
0x180257232  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180257237  mov     eax, 80070057h
0x18025723c  jmp     loc_1802570ED
```
