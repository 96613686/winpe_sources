# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1400761a8`
- end: `0x140076263`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14003f364`

## callees

- `0x140059970`
- `0x1400761a8`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400761e8`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x1400761e8`

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
0x1400761a8  mov     r11, rsp
0x1400761ab  push    rbx
0x1400761ac  sub     rsp, 40h
0x1400761b0  mov     rax, cs:__security_cookie
0x1400761b7  xor     rax, rsp
0x1400761ba  mov     [rsp+48h+var_10], rax
0x1400761bf  mov     eax, edx
0x1400761c1  mov     qword ptr [r11-28h], 0
0x1400761c9  mov     rbx, rcx
0x1400761cc  lea     r9, [r11-20h]
0x1400761d0  xor     ecx, ecx
0x1400761d2  xor     edx, edx
0x1400761d4  test    r8d, r8d
0x1400761d7  mov     [r11-20h], rcx
0x1400761db  mov     [rsp+48h+var_18], ecx
0x1400761df  lea     r8, [r11-28h]
0x1400761e3  setz    dl
0x1400761e6  mov     ecx, eax
0x1400761e8  call    cs:__imp_RtlQueryFeatureConfiguration
0x1400761ef  nop     dword ptr [rax+rax+00h]
0x1400761f4  test    eax, eax
0x1400761f6  jnz     short loc_140076233
0x1400761f8  mov     ecx, [rsp+48h+var_1C]
0x1400761fc  mov     edx, 1
0x140076201  mov     eax, ecx
0x140076203  shr     eax, 4
0x140076206  and     eax, 3
0x140076209  mov     [rbx], eax
0x14007620b  mov     eax, ecx
0x14007620d  shr     eax, 8
0x140076210  and     al, 3Fh
0x140076212  mov     [rbx+4], al
0x140076215  mov     eax, [rsp+48h+var_18]
0x140076219  mov     [rbx+0Ch], eax
0x14007621c  mov     eax, ecx
0x14007621e  shr     eax, 0Eh
0x140076221  and     eax, 3
0x140076224  mov     [rbx+8], eax
0x140076227  mov     eax, ecx
0x140076229  shr     eax, 6
0x14007622c  and     eax, edx
0x14007622e  mov     [rbx+14h], eax
0x140076231  jmp     short loc_140076245
0x140076233  xor     edx, edx
0x140076235  cmp     eax, 117h
0x14007623a  jnz     short loc_14007624D
0x14007623c  mov     ecx, [rsp+48h+var_1C]
0x140076240  mov     edx, 1
0x140076245  shr     ecx, 7
0x140076248  and     ecx, edx
0x14007624a  mov     [rbx+10h], ecx
0x14007624d  mov     eax, edx
0x14007624f  mov     rcx, [rsp+48h+var_10]
0x140076254  xor     rcx, rsp; StackCookie
0x140076257  call    __security_check_cookie
0x14007625c  add     rsp, 40h
0x140076260  pop     rbx
0x140076261  retn
```
