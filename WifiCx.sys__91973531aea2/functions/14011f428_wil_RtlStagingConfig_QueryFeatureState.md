# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14011f428`
- end: `0x14011f515`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140053048`
- `0x14005ae10`

## callees

- `0x1400dfd00`
- `0x14011f428`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14011f46f`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14011f46f`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  int v6; // r9d
  unsigned int v7; // edx
  unsigned int v8; // r8d
  unsigned int v9; // ecx
  __int64 v11; // [rsp+20h] [rbp-28h] BYREF
  __int64 v12; // [rsp+28h] [rbp-20h] BYREF
  int v13; // [rsp+30h] [rbp-18h]

  v11 = 0;
  v12 = 0;
  v13 = 0;
  v6 = RtlQueryFeatureConfiguration(a2, a3 == 0, &v11, &v12);
  if ( v6 )
  {
    v8 = 0;
    if ( v6 == 279 )
    {
      v8 = 1;
      *(_DWORD *)(a1 + 16) = (HIDWORD(v12) >> 7) & 1;
    }
  }
  else
  {
    v7 = HIDWORD(v12);
    v8 = 1;
    v9 = HIDWORD(v12);
    *(_DWORD *)(a1 + 12) = v13;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v9 >> 14;
    *(_DWORD *)a1 = (v9 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v7) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v7 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v7 >> 6) & 1;
  }
  if ( a4 )
    *a4 = v6 != -2147483614;
  return v8;
}

```

## disassembly

```asm
0x14011f428  mov     r11, rsp
0x14011f42b  mov     [r11+18h], rbx
0x14011f42f  push    rdi
0x14011f430  sub     rsp, 40h
0x14011f434  mov     rax, cs:__security_cookie
0x14011f43b  xor     rax, rsp
0x14011f43e  mov     [rsp+48h+var_10], rax
0x14011f443  mov     eax, edx
0x14011f445  mov     qword ptr [r11-28h], 0
0x14011f44d  mov     rbx, rcx
0x14011f450  xor     edx, edx
0x14011f452  xor     ecx, ecx
0x14011f454  mov     rdi, r9
0x14011f457  test    r8d, r8d
0x14011f45a  mov     [r11-20h], rcx
0x14011f45e  mov     [rsp+48h+var_18], ecx
0x14011f462  lea     r9, [r11-20h]
0x14011f466  setz    dl
0x14011f469  lea     r8, [r11-28h]
0x14011f46d  mov     ecx, eax
0x14011f46f  call    cs:__imp_RtlQueryFeatureConfiguration
0x14011f476  nop     dword ptr [rax+rax+00h]
0x14011f47b  mov     r9d, eax
0x14011f47e  test    eax, eax
0x14011f480  jnz     short loc_14011F4C7
0x14011f482  mov     edx, [rsp+48h+var_1C]
0x14011f486  lea     r8d, [r9+1]
0x14011f48a  mov     eax, [rsp+48h+var_18]
0x14011f48e  mov     ecx, edx
0x14011f490  mov     [rbx+0Ch], eax
0x14011f493  mov     eax, edx
0x14011f495  shr     eax, 0Eh
0x14011f498  shr     ecx, 4
0x14011f49b  and     eax, 3
0x14011f49e  and     ecx, 3
0x14011f4a1  mov     [rbx+8], eax
0x14011f4a4  mov     [rbx], ecx
0x14011f4a6  mov     eax, edx
0x14011f4a8  mov     ecx, edx
0x14011f4aa  shr     eax, 6
0x14011f4ad  shr     ecx, 8
0x14011f4b0  and     eax, r8d
0x14011f4b3  and     cl, 3Fh
0x14011f4b6  shr     edx, 7
0x14011f4b9  and     edx, r8d
0x14011f4bc  mov     [rbx+4], cl
0x14011f4bf  mov     [rbx+10h], edx
0x14011f4c2  mov     [rbx+14h], eax
0x14011f4c5  jmp     short loc_14011F4E6
0x14011f4c7  xor     r8d, r8d
0x14011f4ca  cmp     r9d, 117h
0x14011f4d1  jnz     short loc_14011F4E6
0x14011f4d3  mov     ecx, [rsp+48h+var_1C]
0x14011f4d7  mov     r8d, 1
0x14011f4dd  shr     ecx, 7
0x14011f4e0  and     ecx, r8d
0x14011f4e3  mov     [rbx+10h], ecx
0x14011f4e6  test    rdi, rdi
0x14011f4e9  jz      short loc_14011F4F9
0x14011f4eb  xor     ecx, ecx
0x14011f4ed  cmp     r9d, 80000022h
0x14011f4f4  setnz   cl
0x14011f4f7  mov     [rdi], ecx
0x14011f4f9  mov     eax, r8d
0x14011f4fc  mov     rcx, [rsp+48h+var_10]
0x14011f501  xor     rcx, rsp; StackCookie
0x14011f504  call    __security_check_cookie
0x14011f509  mov     rbx, [rsp+48h+arg_10]
0x14011f50e  add     rsp, 40h
0x14011f512  pop     rdi
0x14011f513  retn
```
