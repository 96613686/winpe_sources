# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14000b410`
- end: `0x14000b4cb`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140001f20`

## callees

- `0x1400026d0`
- `0x14000b410`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000b450`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000b450`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // edx
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  int v10; // [rsp+30h] [rbp-18h]

  v8 = 0;
  v9 = 0;
  v10 = 0;
  v4 = RtlQueryFeatureConfiguration(a2, a3 == 0, &v8, &v9);
  if ( !v4 )
  {
    v5 = HIDWORD(v9);
    v6 = 1;
    *(_DWORD *)a1 = (HIDWORD(v9) >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v5) & 0x3F;
    *(_DWORD *)(a1 + 12) = v10;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v5 >> 14;
    *(_DWORD *)(a1 + 20) = (v5 >> 6) & 1;
LABEL_5:
    *(_DWORD *)(a1 + 16) = (v5 >> 7) & 1;
    return v6;
  }
  v6 = 0;
  if ( v4 == 279 )
  {
    v5 = HIDWORD(v9);
    v6 = 1;
    goto LABEL_5;
  }
  return v6;
}

```

## disassembly

```asm
0x14000b410  mov     r11, rsp
0x14000b413  push    rbx
0x14000b414  sub     rsp, 40h
0x14000b418  mov     rax, cs:__security_cookie
0x14000b41f  xor     rax, rsp
0x14000b422  mov     [rsp+48h+var_10], rax
0x14000b427  mov     eax, edx
0x14000b429  mov     qword ptr [r11-28h], 0
0x14000b431  mov     rbx, rcx
0x14000b434  lea     r9, [r11-20h]
0x14000b438  xor     ecx, ecx
0x14000b43a  xor     edx, edx
0x14000b43c  test    r8d, r8d
0x14000b43f  mov     [r11-20h], rcx
0x14000b443  mov     [rsp+48h+var_18], ecx
0x14000b447  lea     r8, [r11-28h]
0x14000b44b  setz    dl
0x14000b44e  mov     ecx, eax
0x14000b450  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000b457  nop     dword ptr [rax+rax+00h]
0x14000b45c  test    eax, eax
0x14000b45e  jnz     short loc_14000B49B
0x14000b460  mov     ecx, [rsp+48h+var_1C]
0x14000b464  mov     edx, 1
0x14000b469  mov     eax, ecx
0x14000b46b  shr     eax, 4
0x14000b46e  and     eax, 3
0x14000b471  mov     [rbx], eax
0x14000b473  mov     eax, ecx
0x14000b475  shr     eax, 8
0x14000b478  and     al, 3Fh
0x14000b47a  mov     [rbx+4], al
0x14000b47d  mov     eax, [rsp+48h+var_18]
0x14000b481  mov     [rbx+0Ch], eax
0x14000b484  mov     eax, ecx
0x14000b486  shr     eax, 0Eh
0x14000b489  and     eax, 3
0x14000b48c  mov     [rbx+8], eax
0x14000b48f  mov     eax, ecx
0x14000b491  shr     eax, 6
0x14000b494  and     eax, edx
0x14000b496  mov     [rbx+14h], eax
0x14000b499  jmp     short loc_14000B4AD
0x14000b49b  xor     edx, edx
0x14000b49d  cmp     eax, 117h
0x14000b4a2  jnz     short loc_14000B4B5
0x14000b4a4  mov     ecx, [rsp+48h+var_1C]
0x14000b4a8  mov     edx, 1
0x14000b4ad  shr     ecx, 7
0x14000b4b0  and     ecx, edx
0x14000b4b2  mov     [rbx+10h], ecx
0x14000b4b5  mov     eax, edx
0x14000b4b7  mov     rcx, [rsp+48h+var_10]
0x14000b4bc  xor     rcx, rsp; StackCookie
0x14000b4bf  call    __security_check_cookie
0x14000b4c4  add     rsp, 40h
0x14000b4c8  pop     rbx
0x14000b4c9  retn
```
