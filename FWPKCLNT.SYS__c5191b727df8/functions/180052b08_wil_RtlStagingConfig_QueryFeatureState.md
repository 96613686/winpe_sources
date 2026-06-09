# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180052b08`
- end: `0x180052bc3`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d518`

## callees

- `0x1800203c0`
- `0x180052b08`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180052b48`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180052b48`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  int v4; // eax
  unsigned int v5; // ecx
  unsigned int v6; // edx
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  int v9; // [rsp+28h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-18h] BYREF

  v10 = 0;
  v8 = 0;
  v9 = 0;
  v4 = RtlQueryFeatureConfiguration(a2, a3 == 0, &v10, &v8);
  if ( !v4 )
  {
    v5 = HIDWORD(v8);
    v6 = 1;
    *(_DWORD *)a1 = (HIDWORD(v8) >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v5) & 0x3F;
    *(_DWORD *)(a1 + 12) = v9;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v5 >> 14;
    *(_DWORD *)(a1 + 20) = (v5 >> 6) & 1;
LABEL_5:
    *(_DWORD *)(a1 + 16) = (v5 >> 7) & 1;
    return v6;
  }
  v6 = 0;
  if ( v4 == 279 )
  {
    v5 = HIDWORD(v8);
    v6 = 1;
    goto LABEL_5;
  }
  return v6;
}

```

## disassembly

```asm
0x180052b08  mov     r11, rsp
0x180052b0b  push    rbx
0x180052b0c  sub     rsp, 40h
0x180052b10  mov     rax, cs:__security_cookie
0x180052b17  xor     rax, rsp
0x180052b1a  mov     [rsp+48h+var_10], rax
0x180052b1f  mov     eax, edx
0x180052b21  mov     qword ptr [r11-18h], 0
0x180052b29  mov     rbx, rcx
0x180052b2c  lea     r9, [r11-28h]
0x180052b30  xor     ecx, ecx
0x180052b32  xor     edx, edx
0x180052b34  test    r8d, r8d
0x180052b37  mov     [r11-28h], rcx
0x180052b3b  mov     [rsp+48h+var_20], ecx
0x180052b3f  lea     r8, [r11-18h]
0x180052b43  setz    dl
0x180052b46  mov     ecx, eax
0x180052b48  call    cs:__imp_RtlQueryFeatureConfiguration
0x180052b4f  nop     dword ptr [rax+rax+00h]
0x180052b54  test    eax, eax
0x180052b56  jnz     short loc_180052B93
0x180052b58  mov     ecx, [rsp+48h+var_24]
0x180052b5c  mov     edx, 1
0x180052b61  mov     eax, ecx
0x180052b63  shr     eax, 4
0x180052b66  and     eax, 3
0x180052b69  mov     [rbx], eax
0x180052b6b  mov     eax, ecx
0x180052b6d  shr     eax, 8
0x180052b70  and     al, 3Fh
0x180052b72  mov     [rbx+4], al
0x180052b75  mov     eax, [rsp+48h+var_20]
0x180052b79  mov     [rbx+0Ch], eax
0x180052b7c  mov     eax, ecx
0x180052b7e  shr     eax, 0Eh
0x180052b81  and     eax, 3
0x180052b84  mov     [rbx+8], eax
0x180052b87  mov     eax, ecx
0x180052b89  shr     eax, 6
0x180052b8c  and     eax, edx
0x180052b8e  mov     [rbx+14h], eax
0x180052b91  jmp     short loc_180052BA5
0x180052b93  xor     edx, edx
0x180052b95  cmp     eax, 117h
0x180052b9a  jnz     short loc_180052BAD
0x180052b9c  mov     ecx, [rsp+48h+var_24]
0x180052ba0  mov     edx, 1
0x180052ba5  shr     ecx, 7
0x180052ba8  and     ecx, edx
0x180052baa  mov     [rbx+10h], ecx
0x180052bad  mov     eax, edx
0x180052baf  mov     rcx, [rsp+48h+var_10]
0x180052bb4  xor     rcx, rsp; StackCookie
0x180052bb7  call    __security_check_cookie
0x180052bbc  add     rsp, 40h
0x180052bc0  pop     rbx
0x180052bc1  retn
```
