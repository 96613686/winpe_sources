# RasSetDeviceConfigInfo

- ea: `0x18001f110`
- end: `0x18001f21c`
- name: `RasSetDeviceConfigInfo`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180011790`
- `0x180011b40`
- `0x18001f110`
- `0x180020fd8`
- `0x180021000`

## pseudocode

```c
__int64 __fastcall RasSetDeviceConfigInfo(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  unsigned int v8; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 551, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  if ( (unsigned int)ValidateConnectionHandle(a1) )
  {
    v12 = SubmitRequest(a1, 0x5Eu, a2, a3, a4);
    v8 = v12;
    if ( !v12 )
    {
LABEL_16:
      v9 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
    }
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_17;
    v10 = 553;
    v11 = v12;
LABEL_15:
    WPP_SF_d(v9[2], v10, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
    goto LABEL_16;
  }
  v8 = -2147024809;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 552;
    v11 = 2147942487LL;
    goto LABEL_15;
  }
LABEL_17:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 6u )
    WPP_SF_d(v9[2], 554, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18001f110  push    rbx
0x18001f112  push    rbp
0x18001f113  push    rsi
0x18001f114  push    rdi
0x18001f115  push    r15
0x18001f117  sub     rsp, 30h
0x18001f11b  mov     rdi, r9
0x18001f11e  mov     esi, r8d
0x18001f121  mov     ebp, edx
0x18001f123  mov     rbx, rcx
0x18001f126  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f12d  lea     r15, WPP_GLOBAL_Control
0x18001f134  cmp     rcx, r15
0x18001f137  jz      short loc_18001F15A
0x18001f139  test    byte ptr [rcx+1Ch], 40h
0x18001f13d  jz      short loc_18001F15A
0x18001f13f  cmp     byte ptr [rcx+19h], 6
0x18001f143  jb      short loc_18001F15A
0x18001f145  mov     rcx, [rcx+10h]
0x18001f149  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f150  mov     edx, 227h
0x18001f155  call    WPP_SF_
0x18001f15a  mov     rcx, rbx
0x18001f15d  call    ValidateConnectionHandle
0x18001f162  test    eax, eax
0x18001f164  jnz     short loc_18001F191
0x18001f166  mov     ebx, 80070057h
0x18001f16b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f172  cmp     rcx, r15
0x18001f175  jz      loc_18001F20F
0x18001f17b  test    byte ptr [rcx+1Ch], 40h
0x18001f17f  jz      short loc_18001F1E6
0x18001f181  cmp     byte ptr [rcx+19h], 2
0x18001f185  jb      short loc_18001F1E6
0x18001f187  mov     edx, 228h
0x18001f18c  mov     r9d, ebx
0x18001f18f  jmp     short loc_18001F1CF
0x18001f191  mov     edx, 5Eh ; '^'
0x18001f196  mov     [rsp+58h+var_38], rdi
0x18001f19b  mov     r9d, esi
0x18001f19e  mov     r8d, ebp
0x18001f1a1  mov     rcx, rbx
0x18001f1a4  call    SubmitRequest
0x18001f1a9  mov     ebx, eax
0x18001f1ab  test    eax, eax
0x18001f1ad  jz      short loc_18001F1DF
0x18001f1af  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1b6  cmp     rcx, r15
0x18001f1b9  jz      short loc_18001F20F
0x18001f1bb  test    byte ptr [rcx+1Ch], 40h
0x18001f1bf  jz      short loc_18001F1E6
0x18001f1c1  cmp     byte ptr [rcx+19h], 2
0x18001f1c5  jb      short loc_18001F1E6
0x18001f1c7  mov     edx, 229h
0x18001f1cc  mov     r9d, eax
0x18001f1cf  mov     rcx, [rcx+10h]
0x18001f1d3  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f1da  call    WPP_SF_d
0x18001f1df  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1e6  cmp     rcx, r15
0x18001f1e9  jz      short loc_18001F20F
0x18001f1eb  test    byte ptr [rcx+1Ch], 40h
0x18001f1ef  jz      short loc_18001F20F
0x18001f1f1  cmp     byte ptr [rcx+19h], 6
0x18001f1f5  jb      short loc_18001F20F
0x18001f1f7  mov     rcx, [rcx+10h]
0x18001f1fb  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18001f202  mov     edx, 22Ah
0x18001f207  mov     r9d, ebx
0x18001f20a  call    WPP_SF_d
0x18001f20f  mov     eax, ebx
0x18001f211  add     rsp, 30h
0x18001f215  pop     r15
0x18001f217  pop     rdi
0x18001f218  pop     rsi
0x18001f219  pop     rbp
0x18001f21a  pop     rbx
0x18001f21b  retn
```
