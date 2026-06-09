# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x140029ff0`
- end: `0x14002a0ab`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000540c`

## callees

- `0x14001adc0`
- `0x140029ff0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002a030`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002a030`

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
0x140029ff0  mov     r11, rsp
0x140029ff3  push    rbx
0x140029ff4  sub     rsp, 40h
0x140029ff8  mov     rax, cs:__security_cookie
0x140029fff  xor     rax, rsp
0x14002a002  mov     [rsp+48h+var_10], rax
0x14002a007  mov     eax, edx
0x14002a009  mov     qword ptr [r11-28h], 0
0x14002a011  mov     rbx, rcx
0x14002a014  lea     r9, [r11-20h]
0x14002a018  xor     ecx, ecx
0x14002a01a  xor     edx, edx
0x14002a01c  test    r8d, r8d
0x14002a01f  mov     [r11-20h], rcx
0x14002a023  mov     [rsp+48h+var_18], ecx
0x14002a027  lea     r8, [r11-28h]
0x14002a02b  setz    dl
0x14002a02e  mov     ecx, eax
0x14002a030  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002a037  nop     dword ptr [rax+rax+00h]
0x14002a03c  test    eax, eax
0x14002a03e  jnz     short loc_14002A07B
0x14002a040  mov     ecx, [rsp+48h+var_1C]
0x14002a044  mov     edx, 1
0x14002a049  mov     eax, ecx
0x14002a04b  shr     eax, 4
0x14002a04e  and     eax, 3
0x14002a051  mov     [rbx], eax
0x14002a053  mov     eax, ecx
0x14002a055  shr     eax, 8
0x14002a058  and     al, 3Fh
0x14002a05a  mov     [rbx+4], al
0x14002a05d  mov     eax, [rsp+48h+var_18]
0x14002a061  mov     [rbx+0Ch], eax
0x14002a064  mov     eax, ecx
0x14002a066  shr     eax, 0Eh
0x14002a069  and     eax, 3
0x14002a06c  mov     [rbx+8], eax
0x14002a06f  mov     eax, ecx
0x14002a071  shr     eax, 6
0x14002a074  and     eax, edx
0x14002a076  mov     [rbx+14h], eax
0x14002a079  jmp     short loc_14002A08D
0x14002a07b  xor     edx, edx
0x14002a07d  cmp     eax, 117h
0x14002a082  jnz     short loc_14002A095
0x14002a084  mov     ecx, [rsp+48h+var_1C]
0x14002a088  mov     edx, 1
0x14002a08d  shr     ecx, 7
0x14002a090  and     ecx, edx
0x14002a092  mov     [rbx+10h], ecx
0x14002a095  mov     eax, edx
0x14002a097  mov     rcx, [rsp+48h+var_10]
0x14002a09c  xor     rcx, rsp; StackCookie
0x14002a09f  call    __security_check_cookie
0x14002a0a4  add     rsp, 40h
0x14002a0a8  pop     rbx
0x14002a0a9  retn
```
