# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1400273e8`
- end: `0x1400274a3`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140002990`

## callees

- `0x140006a20`
- `0x1400273e8`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140027428`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140027428`

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
0x1400273e8  mov     r11, rsp
0x1400273eb  push    rbx
0x1400273ec  sub     rsp, 40h
0x1400273f0  mov     rax, cs:__security_cookie
0x1400273f7  xor     rax, rsp
0x1400273fa  mov     [rsp+48h+var_10], rax
0x1400273ff  mov     eax, edx
0x140027401  mov     qword ptr [r11-28h], 0
0x140027409  mov     rbx, rcx
0x14002740c  lea     r9, [r11-20h]
0x140027410  xor     ecx, ecx
0x140027412  xor     edx, edx
0x140027414  test    r8d, r8d
0x140027417  mov     [r11-20h], rcx
0x14002741b  mov     [rsp+48h+var_18], ecx
0x14002741f  lea     r8, [r11-28h]
0x140027423  setz    dl
0x140027426  mov     ecx, eax
0x140027428  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002742f  nop     dword ptr [rax+rax+00h]
0x140027434  test    eax, eax
0x140027436  jnz     short loc_140027473
0x140027438  mov     ecx, [rsp+48h+var_1C]
0x14002743c  mov     edx, 1
0x140027441  mov     eax, ecx
0x140027443  shr     eax, 4
0x140027446  and     eax, 3
0x140027449  mov     [rbx], eax
0x14002744b  mov     eax, ecx
0x14002744d  shr     eax, 8
0x140027450  and     al, 3Fh
0x140027452  mov     [rbx+4], al
0x140027455  mov     eax, [rsp+48h+var_18]
0x140027459  mov     [rbx+0Ch], eax
0x14002745c  mov     eax, ecx
0x14002745e  shr     eax, 0Eh
0x140027461  and     eax, 3
0x140027464  mov     [rbx+8], eax
0x140027467  mov     eax, ecx
0x140027469  shr     eax, 6
0x14002746c  and     eax, edx
0x14002746e  mov     [rbx+14h], eax
0x140027471  jmp     short loc_140027485
0x140027473  xor     edx, edx
0x140027475  cmp     eax, 117h
0x14002747a  jnz     short loc_14002748D
0x14002747c  mov     ecx, [rsp+48h+var_1C]
0x140027480  mov     edx, 1
0x140027485  shr     ecx, 7
0x140027488  and     ecx, edx
0x14002748a  mov     [rbx+10h], ecx
0x14002748d  mov     eax, edx
0x14002748f  mov     rcx, [rsp+48h+var_10]
0x140027494  xor     rcx, rsp; StackCookie
0x140027497  call    __security_check_cookie
0x14002749c  add     rsp, 40h
0x1400274a0  pop     rbx
0x1400274a1  retn
```
