# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14007a8f0`
- end: `0x14007a9ab`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002e650`

## callees

- `0x14005c7d0`
- `0x14007a8f0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14007a930`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14007a930`

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
0x14007a8f0  mov     r11, rsp
0x14007a8f3  push    rbx
0x14007a8f4  sub     rsp, 40h
0x14007a8f8  mov     rax, cs:__security_cookie
0x14007a8ff  xor     rax, rsp
0x14007a902  mov     [rsp+48h+var_10], rax
0x14007a907  mov     eax, edx
0x14007a909  mov     qword ptr [r11-28h], 0
0x14007a911  mov     rbx, rcx
0x14007a914  lea     r9, [r11-20h]
0x14007a918  xor     ecx, ecx
0x14007a91a  xor     edx, edx
0x14007a91c  test    r8d, r8d
0x14007a91f  mov     [r11-20h], rcx
0x14007a923  mov     [rsp+48h+var_18], ecx
0x14007a927  lea     r8, [r11-28h]
0x14007a92b  setz    dl
0x14007a92e  mov     ecx, eax
0x14007a930  call    cs:__imp_RtlQueryFeatureConfiguration
0x14007a937  nop     dword ptr [rax+rax+00h]
0x14007a93c  test    eax, eax
0x14007a93e  jnz     short loc_14007A97B
0x14007a940  mov     ecx, [rsp+48h+var_1C]
0x14007a944  mov     edx, 1
0x14007a949  mov     eax, ecx
0x14007a94b  shr     eax, 4
0x14007a94e  and     eax, 3
0x14007a951  mov     [rbx], eax
0x14007a953  mov     eax, ecx
0x14007a955  shr     eax, 8
0x14007a958  and     al, 3Fh
0x14007a95a  mov     [rbx+4], al
0x14007a95d  mov     eax, [rsp+48h+var_18]
0x14007a961  mov     [rbx+0Ch], eax
0x14007a964  mov     eax, ecx
0x14007a966  shr     eax, 0Eh
0x14007a969  and     eax, 3
0x14007a96c  mov     [rbx+8], eax
0x14007a96f  mov     eax, ecx
0x14007a971  shr     eax, 6
0x14007a974  and     eax, edx
0x14007a976  mov     [rbx+14h], eax
0x14007a979  jmp     short loc_14007A98D
0x14007a97b  xor     edx, edx
0x14007a97d  cmp     eax, 117h
0x14007a982  jnz     short loc_14007A995
0x14007a984  mov     ecx, [rsp+48h+var_1C]
0x14007a988  mov     edx, 1
0x14007a98d  shr     ecx, 7
0x14007a990  and     ecx, edx
0x14007a992  mov     [rbx+10h], ecx
0x14007a995  mov     eax, edx
0x14007a997  mov     rcx, [rsp+48h+var_10]
0x14007a99c  xor     rcx, rsp; StackCookie
0x14007a99f  call    __security_check_cookie
0x14007a9a4  add     rsp, 40h
0x14007a9a8  pop     rbx
0x14007a9a9  retn
```
