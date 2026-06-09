# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14002b064`
- end: `0x14002b11f`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004ea0`

## callees

- `0x1400079f0`
- `0x14002b064`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002b0a4`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002b0a4`

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
0x14002b064  mov     r11, rsp
0x14002b067  push    rbx
0x14002b068  sub     rsp, 40h
0x14002b06c  mov     rax, cs:__security_cookie
0x14002b073  xor     rax, rsp
0x14002b076  mov     [rsp+48h+var_10], rax
0x14002b07b  mov     eax, edx
0x14002b07d  mov     qword ptr [r11-28h], 0
0x14002b085  mov     rbx, rcx
0x14002b088  lea     r9, [r11-20h]
0x14002b08c  xor     ecx, ecx
0x14002b08e  xor     edx, edx
0x14002b090  test    r8d, r8d
0x14002b093  mov     [r11-20h], rcx
0x14002b097  mov     [rsp+48h+var_18], ecx
0x14002b09b  lea     r8, [r11-28h]
0x14002b09f  setz    dl
0x14002b0a2  mov     ecx, eax
0x14002b0a4  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002b0ab  nop     dword ptr [rax+rax+00h]
0x14002b0b0  test    eax, eax
0x14002b0b2  jnz     short loc_14002B0EF
0x14002b0b4  mov     ecx, [rsp+48h+var_1C]
0x14002b0b8  mov     edx, 1
0x14002b0bd  mov     eax, ecx
0x14002b0bf  shr     eax, 4
0x14002b0c2  and     eax, 3
0x14002b0c5  mov     [rbx], eax
0x14002b0c7  mov     eax, ecx
0x14002b0c9  shr     eax, 8
0x14002b0cc  and     al, 3Fh
0x14002b0ce  mov     [rbx+4], al
0x14002b0d1  mov     eax, [rsp+48h+var_18]
0x14002b0d5  mov     [rbx+0Ch], eax
0x14002b0d8  mov     eax, ecx
0x14002b0da  shr     eax, 0Eh
0x14002b0dd  and     eax, 3
0x14002b0e0  mov     [rbx+8], eax
0x14002b0e3  mov     eax, ecx
0x14002b0e5  shr     eax, 6
0x14002b0e8  and     eax, edx
0x14002b0ea  mov     [rbx+14h], eax
0x14002b0ed  jmp     short loc_14002B101
0x14002b0ef  xor     edx, edx
0x14002b0f1  cmp     eax, 117h
0x14002b0f6  jnz     short loc_14002B109
0x14002b0f8  mov     ecx, [rsp+48h+var_1C]
0x14002b0fc  mov     edx, 1
0x14002b101  shr     ecx, 7
0x14002b104  and     ecx, edx
0x14002b106  mov     [rbx+10h], ecx
0x14002b109  mov     eax, edx
0x14002b10b  mov     rcx, [rsp+48h+var_10]
0x14002b110  xor     rcx, rsp; StackCookie
0x14002b113  call    __security_check_cookie
0x14002b118  add     rsp, 40h
0x14002b11c  pop     rbx
0x14002b11d  retn
```
