# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140021710`
- end: `0x1400217c0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140021670`

## callees

- `0x140011224`
- `0x140013950`
- `0x14002138c`
- `0x140021710`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140021760`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140021760`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  __int64 *i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 *)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (volatile signed __int32 **)result;
    if ( !result )
      break;
    if ( !*(_BYTE *)(result + 29) && !*(_BYTE *)(result + 30) && !*(_BYTE *)(result + 28) )
    {
      v1 = *(unsigned int *)(result + 24);
      v7 = 0;
      v8 = 0;
      v6 = 0;
      v2 = RtlQueryFeatureConfiguration(v1, 1, &v6, &v7);
      v5 = 0;
      wil_details_BuildFeatureStateCacheFromQueryResults(v2, &v7, &v5);
      _InterlockedXor(*v4, ((unsigned __int16)v5 ^ (unsigned __int16)**v4) & 0xF80);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140021710  push    rbx
0x140021712  sub     rsp, 50h
0x140021716  mov     rax, cs:__security_cookie
0x14002171d  xor     rax, rsp
0x140021720  mov     [rsp+58h+var_18], rax
0x140021725  lea     rcx, wil_details_featureDescriptors_a
0x14002172c  jmp     short loc_14002179F
0x14002172e  cmp     byte ptr [rbx+1Dh], 0
0x140021732  jnz     short loc_14002179B
0x140021734  cmp     byte ptr [rbx+1Eh], 0
0x140021738  jnz     short loc_14002179B
0x14002173a  cmp     byte ptr [rbx+1Ch], 0
0x14002173e  jnz     short loc_14002179B
0x140021740  mov     ecx, [rbx+18h]
0x140021743  lea     r9, [rsp+58h+var_28]
0x140021748  xor     eax, eax
0x14002174a  lea     r8, [rsp+58h+var_30]
0x14002174f  mov     [rsp+58h+var_28], rax
0x140021754  mov     [rsp+58h+var_20], eax
0x140021758  mov     [rsp+58h+var_30], rax
0x14002175d  lea     edx, [rax+1]
0x140021760  call    cs:__imp_RtlQueryFeatureConfiguration
0x140021767  nop     dword ptr [rax+rax+00h]
0x14002176c  lea     r8, [rsp+58h+var_38]
0x140021771  mov     [rsp+58h+var_38], 0
0x14002177a  mov     ecx, eax
0x14002177c  lea     rdx, [rsp+58h+var_28]
0x140021781  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140021786  mov     rcx, [rbx]
0x140021789  mov     edx, [rcx]
0x14002178b  xor     edx, dword ptr [rsp+58h+var_38]
0x14002178f  mov     rax, [rbx]
0x140021792  and     edx, 0F80h
0x140021798  lock xor [rax], edx
0x14002179b  lea     rcx, [rbx+38h]
0x14002179f  call    wil_details_FeatureDescriptors_SkipPadding
0x1400217a4  mov     rbx, rax
0x1400217a7  test    rax, rax
0x1400217aa  jnz     short loc_14002172E
0x1400217ac  mov     rcx, [rsp+58h+var_18]
0x1400217b1  xor     rcx, rsp; StackCookie
0x1400217b4  call    __security_check_cookie
0x1400217b9  add     rsp, 50h
0x1400217bd  pop     rbx
0x1400217be  retn
```
