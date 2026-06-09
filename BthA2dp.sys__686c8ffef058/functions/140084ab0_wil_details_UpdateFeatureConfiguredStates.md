# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140084ab0`
- end: `0x140084b60`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140084a10`

## callees

- `0x14003cdc8`
- `0x14005c7d0`
- `0x14008472c`
- `0x140084ab0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140084b00`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140084b00`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  __int64 **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 **)(v4 + 7) )
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
0x140084ab0  push    rbx
0x140084ab2  sub     rsp, 50h
0x140084ab6  mov     rax, cs:__security_cookie
0x140084abd  xor     rax, rsp
0x140084ac0  mov     [rsp+58h+var_18], rax
0x140084ac5  lea     rcx, wil_details_featureDescriptors_a
0x140084acc  jmp     short loc_140084B3F
0x140084ace  cmp     byte ptr [rbx+1Dh], 0
0x140084ad2  jnz     short loc_140084B3B
0x140084ad4  cmp     byte ptr [rbx+1Eh], 0
0x140084ad8  jnz     short loc_140084B3B
0x140084ada  cmp     byte ptr [rbx+1Ch], 0
0x140084ade  jnz     short loc_140084B3B
0x140084ae0  mov     ecx, [rbx+18h]
0x140084ae3  lea     r9, [rsp+58h+var_28]
0x140084ae8  xor     eax, eax
0x140084aea  lea     r8, [rsp+58h+var_30]
0x140084aef  mov     [rsp+58h+var_28], rax
0x140084af4  mov     [rsp+58h+var_20], eax
0x140084af8  mov     [rsp+58h+var_30], rax
0x140084afd  lea     edx, [rax+1]
0x140084b00  call    cs:__imp_RtlQueryFeatureConfiguration
0x140084b07  nop     dword ptr [rax+rax+00h]
0x140084b0c  lea     r8, [rsp+58h+var_38]
0x140084b11  mov     [rsp+58h+var_38], 0
0x140084b1a  mov     ecx, eax
0x140084b1c  lea     rdx, [rsp+58h+var_28]
0x140084b21  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140084b26  mov     rcx, [rbx]
0x140084b29  mov     edx, [rcx]
0x140084b2b  xor     edx, dword ptr [rsp+58h+var_38]
0x140084b2f  mov     rax, [rbx]
0x140084b32  and     edx, 0F80h
0x140084b38  lock xor [rax], edx
0x140084b3b  lea     rcx, [rbx+38h]
0x140084b3f  call    wil_details_FeatureDescriptors_SkipPadding
0x140084b44  mov     rbx, rax
0x140084b47  test    rax, rax
0x140084b4a  jnz     short loc_140084ACE
0x140084b4c  mov     rcx, [rsp+58h+var_18]
0x140084b51  xor     rcx, rsp; StackCookie
0x140084b54  call    __security_check_cookie
0x140084b59  add     rsp, 50h
0x140084b5d  pop     rbx
0x140084b5e  retn
```
