# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14002a490`
- end: `0x14002a540`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14002a3f0`

## callees

- `0x140004dd8`
- `0x14001adc0`
- `0x14002a114`
- `0x14002a490`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002a4e0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002a4e0`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  int **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
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
0x14002a490  push    rbx
0x14002a492  sub     rsp, 50h
0x14002a496  mov     rax, cs:__security_cookie
0x14002a49d  xor     rax, rsp
0x14002a4a0  mov     [rsp+58h+var_18], rax
0x14002a4a5  lea     rcx, wil_details_featureDescriptors_a
0x14002a4ac  jmp     short loc_14002A51F
0x14002a4ae  cmp     byte ptr [rbx+1Dh], 0
0x14002a4b2  jnz     short loc_14002A51B
0x14002a4b4  cmp     byte ptr [rbx+1Eh], 0
0x14002a4b8  jnz     short loc_14002A51B
0x14002a4ba  cmp     byte ptr [rbx+1Ch], 0
0x14002a4be  jnz     short loc_14002A51B
0x14002a4c0  mov     ecx, [rbx+18h]
0x14002a4c3  lea     r9, [rsp+58h+var_28]
0x14002a4c8  xor     eax, eax
0x14002a4ca  lea     r8, [rsp+58h+var_30]
0x14002a4cf  mov     [rsp+58h+var_28], rax
0x14002a4d4  mov     [rsp+58h+var_20], eax
0x14002a4d8  mov     [rsp+58h+var_30], rax
0x14002a4dd  lea     edx, [rax+1]
0x14002a4e0  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002a4e7  nop     dword ptr [rax+rax+00h]
0x14002a4ec  lea     r8, [rsp+58h+var_38]
0x14002a4f1  mov     [rsp+58h+var_38], 0
0x14002a4fa  mov     ecx, eax
0x14002a4fc  lea     rdx, [rsp+58h+var_28]
0x14002a501  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14002a506  mov     rcx, [rbx]
0x14002a509  mov     edx, [rcx]
0x14002a50b  xor     edx, dword ptr [rsp+58h+var_38]
0x14002a50f  mov     rax, [rbx]
0x14002a512  and     edx, 0F80h
0x14002a518  lock xor [rax], edx
0x14002a51b  lea     rcx, [rbx+38h]
0x14002a51f  call    wil_details_FeatureDescriptors_SkipPadding
0x14002a524  mov     rbx, rax
0x14002a527  test    rax, rax
0x14002a52a  jnz     short loc_14002A4AE
0x14002a52c  mov     rcx, [rsp+58h+var_18]
0x14002a531  xor     rcx, rsp; StackCookie
0x14002a534  call    __security_check_cookie
0x14002a539  add     rsp, 50h
0x14002a53d  pop     rbx
0x14002a53e  retn
```
