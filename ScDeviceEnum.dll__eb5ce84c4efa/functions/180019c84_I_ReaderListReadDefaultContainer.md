# I_ReaderListReadDefaultContainer

- ea: `0x180019c84`
- end: `0x180019d64`
- name: `I_ReaderListReadDefaultContainer`
- size: `224`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001317c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180019250`
- `0x180019c84`
- `0x18001cc6c`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadDefaultContainer(__int64 a1, __int64 a2, _DWORD *a3)
{
  PVOID v6; // rcx
  HCRYPTPROV v7; // r8
  const wchar_t *v8; // r9
  unsigned int ContainerDataPerKeyType; // ebx

  WppTraceIndent(a1, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  v7 = *(_QWORD *)(a2 + 128);
  *a3 = 0;
  if ( v7 && (v8 = *(const wchar_t **)(a2 + 96)) != 0 )
  {
    ContainerDataPerKeyType = I_ReaderListReadContainerDataPerKeyType(a1, a2, v7, v8, 1u);
    if ( !ContainerDataPerKeyType )
      ++*a3;
  }
  else
  {
    ContainerDataPerKeyType = -2146893802;
  }
  WppTraceIndent(v6, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      ContainerDataPerKeyType);
  }
  return ContainerDataPerKeyType;
}

```

## disassembly

```asm
0x180019c84  push    rbx
0x180019c86  push    rsi
0x180019c87  push    rdi
0x180019c88  push    r14
0x180019c8a  sub     rsp, 38h
0x180019c8e  mov     rbx, rdx
0x180019c91  mov     rdi, r8
0x180019c94  xor     edx, edx
0x180019c96  mov     rsi, rcx
0x180019c99  call    WppTraceIndent
0x180019c9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ca5  lea     r14, WPP_GLOBAL_Control
0x180019cac  cmp     rcx, r14
0x180019caf  jz      short loc_180019CD9
0x180019cb1  test    byte ptr [rcx+1Ch], 2
0x180019cb5  jz      short loc_180019CD9
0x180019cb7  cmp     byte ptr [rcx+19h], 5
0x180019cbb  jb      short loc_180019CD9
0x180019cbd  mov     r9, cs:WPP_pszIndent
0x180019cc4  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180019ccb  mov     rcx, [rcx+10h]
0x180019ccf  mov     edx, 5Ch ; '\'
0x180019cd4  call    WPP_SF_s
0x180019cd9  mov     r8, [rbx+80h]
0x180019ce0  mov     dword ptr [rdi], 0
0x180019ce6  test    r8, r8
0x180019ce9  jz      short loc_180019D11
0x180019ceb  mov     r9, [rbx+60h]
0x180019cef  test    r9, r9
0x180019cf2  jz      short loc_180019D11
0x180019cf4  mov     rdx, rbx
0x180019cf7  mov     [rsp+58h+var_38], 1
0x180019cff  mov     rcx, rsi
0x180019d02  call    I_ReaderListReadContainerDataPerKeyType
0x180019d07  mov     ebx, eax
0x180019d09  test    eax, eax
0x180019d0b  jnz     short loc_180019D16
0x180019d0d  inc     dword ptr [rdi]
0x180019d0f  jmp     short loc_180019D16
0x180019d11  mov     ebx, 80090016h
0x180019d16  mov     edx, 1
0x180019d1b  call    WppTraceIndent
0x180019d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d27  cmp     rcx, r14
0x180019d2a  jz      short loc_180019D58
0x180019d2c  test    byte ptr [rcx+1Ch], 2
0x180019d30  jz      short loc_180019D58
0x180019d32  cmp     byte ptr [rcx+19h], 5
0x180019d36  jb      short loc_180019D58
0x180019d38  mov     r9, cs:WPP_pszIndent
0x180019d3f  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180019d46  mov     rcx, [rcx+10h]
0x180019d4a  mov     edx, 5Dh ; ']'
0x180019d4f  mov     [rsp+58h+var_38], ebx
0x180019d53  call    WPP_SF_sd
0x180019d58  mov     eax, ebx
0x180019d5a  add     rsp, 38h
0x180019d5e  pop     r14
0x180019d60  pop     rdi
0x180019d61  pop     rsi
0x180019d62  pop     rbx
0x180019d63  retn
```
