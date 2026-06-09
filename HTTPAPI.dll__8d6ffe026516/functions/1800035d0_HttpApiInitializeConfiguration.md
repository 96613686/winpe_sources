# HttpApiInitializeConfiguration

- ea: `0x1800035d0`
- end: `0x180003658`
- name: `HttpApiInitializeConfiguration`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800034a0`

## callees

- `0x1800035d0`
- `0x180004380`
- `0x18000bdd0`
- `0x18000be2c`

## pseudocode

```c
__int64 __fastcall HttpApiInitializeConfiguration(__int64 a1, __int64 a2, __int64 a3)
{
  char v3; // di
  unsigned int v4; // ebx
  int v5; // eax

  v3 = a1;
  v4 = 87;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_L(a1, 16, WPP_d1f5b049c58935796a293ebb03e09278_Traceguids);
  if ( (v3 & 0x17) != 0 )
  {
    v5 = dword_18001276C;
    if ( !dword_18001276C )
    {
      v4 = InitializeConfigurationGlobals();
      if ( v4 )
        goto LABEL_8;
      v5 = dword_18001276C;
      goto LABEL_7;
    }
    v4 = 0;
    if ( dword_18001276C != -1 )
    {
LABEL_7:
      dword_18001276C = v5 + 1;
      goto LABEL_8;
    }
    v4 = 103;
  }
LABEL_8:
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_Dd(a1, 17, a3, v4);
  return v4;
}

```

## disassembly

```asm
0x1800035d0  mov     [rsp+arg_0], rbx
0x1800035d5  push    rdi
0x1800035d6  sub     rsp, 30h
0x1800035da  mov     edi, ecx
0x1800035dc  mov     ebx, 57h ; 'W'
0x1800035e1  test    cs:byte_1800126A3, 4
0x1800035e8  jz      short loc_1800035FE
0x1800035ea  mov     edx, 10h
0x1800035ef  lea     r8, WPP_d1f5b049c58935796a293ebb03e09278_Traceguids
0x1800035f6  mov     r9d, ecx
0x1800035f9  call    WPP_SF_L
0x1800035fe  test    dil, 17h
0x180003602  jz      short loc_180003627
0x180003604  mov     eax, cs:dword_18001276C
0x18000360a  test    eax, eax
0x18000360c  jnz     short loc_18000364A
0x18000360e  call    InitializeConfigurationGlobals
0x180003613  mov     ebx, eax
0x180003615  test    eax, eax
0x180003617  jnz     short loc_180003627
0x180003619  mov     eax, cs:dword_18001276C
0x18000361f  inc     eax
0x180003621  mov     cs:dword_18001276C, eax
0x180003627  test    cs:byte_1800126A3, 4
0x18000362e  jz      short loc_18000363D
0x180003630  mov     edx, 11h
0x180003635  mov     r9d, ebx
0x180003638  call    WPP_SF_Dd
0x18000363d  mov     eax, ebx
0x18000363f  mov     rbx, [rsp+38h+arg_0]
0x180003644  add     rsp, 30h
0x180003648  pop     rdi
0x180003649  retn
0x18000364a  xor     ebx, ebx
0x18000364c  cmp     eax, 0FFFFFFFFh
0x18000364f  jnz     short loc_18000361F
0x180003651  mov     ebx, 67h ; 'g'
0x180003656  jmp     short loc_180003627
```
