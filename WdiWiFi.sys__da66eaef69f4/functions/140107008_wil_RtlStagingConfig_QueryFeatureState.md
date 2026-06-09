# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x140107008`
- end: `0x1401070c3`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400a53d0`
- `0x1400a54e8`

## callees

- `0x1400da4f0`
- `0x140107008`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140107048`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140107048`

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
0x140107008  mov     r11, rsp
0x14010700b  push    rbx
0x14010700c  sub     rsp, 40h
0x140107010  mov     rax, cs:__security_cookie
0x140107017  xor     rax, rsp
0x14010701a  mov     [rsp+48h+var_10], rax
0x14010701f  mov     eax, edx
0x140107021  mov     qword ptr [r11-28h], 0
0x140107029  mov     rbx, rcx
0x14010702c  lea     r9, [r11-20h]
0x140107030  xor     ecx, ecx
0x140107032  xor     edx, edx
0x140107034  test    r8d, r8d
0x140107037  mov     [r11-20h], rcx
0x14010703b  mov     [rsp+48h+var_18], ecx
0x14010703f  lea     r8, [r11-28h]
0x140107043  setz    dl
0x140107046  mov     ecx, eax
0x140107048  call    cs:__imp_RtlQueryFeatureConfiguration
0x14010704f  nop     dword ptr [rax+rax+00h]
0x140107054  test    eax, eax
0x140107056  jnz     short loc_140107093
0x140107058  mov     ecx, [rsp+48h+var_1C]
0x14010705c  mov     edx, 1
0x140107061  mov     eax, ecx
0x140107063  shr     eax, 4
0x140107066  and     eax, 3
0x140107069  mov     [rbx], eax
0x14010706b  mov     eax, ecx
0x14010706d  shr     eax, 8
0x140107070  and     al, 3Fh
0x140107072  mov     [rbx+4], al
0x140107075  mov     eax, [rsp+48h+var_18]
0x140107079  mov     [rbx+0Ch], eax
0x14010707c  mov     eax, ecx
0x14010707e  shr     eax, 0Eh
0x140107081  and     eax, 3
0x140107084  mov     [rbx+8], eax
0x140107087  mov     eax, ecx
0x140107089  shr     eax, 6
0x14010708c  and     eax, edx
0x14010708e  mov     [rbx+14h], eax
0x140107091  jmp     short loc_1401070A5
0x140107093  xor     edx, edx
0x140107095  cmp     eax, 117h
0x14010709a  jnz     short loc_1401070AD
0x14010709c  mov     ecx, [rsp+48h+var_1C]
0x1401070a0  mov     edx, 1
0x1401070a5  shr     ecx, 7
0x1401070a8  and     ecx, edx
0x1401070aa  mov     [rbx+10h], ecx
0x1401070ad  mov     eax, edx
0x1401070af  mov     rcx, [rsp+48h+var_10]
0x1401070b4  xor     rcx, rsp; StackCookie
0x1401070b7  call    __security_check_cookie
0x1401070bc  add     rsp, 40h
0x1401070c0  pop     rbx
0x1401070c1  retn
```
