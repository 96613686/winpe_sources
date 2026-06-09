# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14001e7c0`
- end: `0x14001e87b`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004db4`

## callees

- `0x140013860`
- `0x14001e7c0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001e800`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001e800`

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
0x14001e7c0  mov     r11, rsp
0x14001e7c3  push    rbx
0x14001e7c4  sub     rsp, 40h
0x14001e7c8  mov     rax, cs:__security_cookie
0x14001e7cf  xor     rax, rsp
0x14001e7d2  mov     [rsp+48h+var_10], rax
0x14001e7d7  mov     eax, edx
0x14001e7d9  mov     qword ptr [r11-28h], 0
0x14001e7e1  mov     rbx, rcx
0x14001e7e4  lea     r9, [r11-20h]
0x14001e7e8  xor     ecx, ecx
0x14001e7ea  xor     edx, edx
0x14001e7ec  test    r8d, r8d
0x14001e7ef  mov     [r11-20h], rcx
0x14001e7f3  mov     [rsp+48h+var_18], ecx
0x14001e7f7  lea     r8, [r11-28h]
0x14001e7fb  setz    dl
0x14001e7fe  mov     ecx, eax
0x14001e800  call    cs:__imp_RtlQueryFeatureConfiguration
0x14001e807  nop     dword ptr [rax+rax+00h]
0x14001e80c  test    eax, eax
0x14001e80e  jnz     short loc_14001E84B
0x14001e810  mov     ecx, [rsp+48h+var_1C]
0x14001e814  mov     edx, 1
0x14001e819  mov     eax, ecx
0x14001e81b  shr     eax, 4
0x14001e81e  and     eax, 3
0x14001e821  mov     [rbx], eax
0x14001e823  mov     eax, ecx
0x14001e825  shr     eax, 8
0x14001e828  and     al, 3Fh
0x14001e82a  mov     [rbx+4], al
0x14001e82d  mov     eax, [rsp+48h+var_18]
0x14001e831  mov     [rbx+0Ch], eax
0x14001e834  mov     eax, ecx
0x14001e836  shr     eax, 0Eh
0x14001e839  and     eax, 3
0x14001e83c  mov     [rbx+8], eax
0x14001e83f  mov     eax, ecx
0x14001e841  shr     eax, 6
0x14001e844  and     eax, edx
0x14001e846  mov     [rbx+14h], eax
0x14001e849  jmp     short loc_14001E85D
0x14001e84b  xor     edx, edx
0x14001e84d  cmp     eax, 117h
0x14001e852  jnz     short loc_14001E865
0x14001e854  mov     ecx, [rsp+48h+var_1C]
0x14001e858  mov     edx, 1
0x14001e85d  shr     ecx, 7
0x14001e860  and     ecx, edx
0x14001e862  mov     [rbx+10h], ecx
0x14001e865  mov     eax, edx
0x14001e867  mov     rcx, [rsp+48h+var_10]
0x14001e86c  xor     rcx, rsp; StackCookie
0x14001e86f  call    __security_check_cookie
0x14001e874  add     rsp, 40h
0x14001e878  pop     rbx
0x14001e879  retn
```
