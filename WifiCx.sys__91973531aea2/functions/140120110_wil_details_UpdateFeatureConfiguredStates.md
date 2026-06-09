# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140120110`
- end: `0x1401201c0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140120070`

## callees

- `0x1400d94bc`
- `0x1400dfd00`
- `0x14011fd90`
- `0x140120110`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140120160`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140120160`

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

  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
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
0x140120110  push    rbx
0x140120112  sub     rsp, 50h
0x140120116  mov     rax, cs:__security_cookie
0x14012011d  xor     rax, rsp
0x140120120  mov     [rsp+58h+var_18], rax
0x140120125  lea     rcx, wil_details_featureDescriptors_a
0x14012012c  jmp     short loc_14012019F
0x14012012e  cmp     byte ptr [rbx+1Dh], 0
0x140120132  jnz     short loc_14012019B
0x140120134  cmp     byte ptr [rbx+1Eh], 0
0x140120138  jnz     short loc_14012019B
0x14012013a  cmp     byte ptr [rbx+1Ch], 0
0x14012013e  jnz     short loc_14012019B
0x140120140  mov     ecx, [rbx+18h]
0x140120143  lea     r9, [rsp+58h+var_28]
0x140120148  xor     eax, eax
0x14012014a  lea     r8, [rsp+58h+var_30]
0x14012014f  mov     [rsp+58h+var_28], rax
0x140120154  mov     [rsp+58h+var_20], eax
0x140120158  mov     [rsp+58h+var_30], rax
0x14012015d  lea     edx, [rax+1]
0x140120160  call    cs:__imp_RtlQueryFeatureConfiguration
0x140120167  nop     dword ptr [rax+rax+00h]
0x14012016c  lea     r8, [rsp+58h+var_38]
0x140120171  mov     [rsp+58h+var_38], 0
0x14012017a  mov     ecx, eax
0x14012017c  lea     rdx, [rsp+58h+var_28]
0x140120181  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140120186  mov     rcx, [rbx]
0x140120189  mov     edx, [rcx]
0x14012018b  xor     edx, dword ptr [rsp+58h+var_38]
0x14012018f  mov     rax, [rbx]
0x140120192  and     edx, 0F80h
0x140120198  lock xor [rax], edx
0x14012019b  lea     rcx, [rbx+38h]
0x14012019f  call    wil_details_FeatureDescriptors_SkipPadding
0x1401201a4  mov     rbx, rax
0x1401201a7  test    rax, rax
0x1401201aa  jnz     short loc_14012012E
0x1401201ac  mov     rcx, [rsp+58h+var_18]
0x1401201b1  xor     rcx, rsp; StackCookie
0x1401201b4  call    __security_check_cookie
0x1401201b9  add     rsp, 50h
0x1401201bd  pop     rbx
0x1401201be  retn
```
