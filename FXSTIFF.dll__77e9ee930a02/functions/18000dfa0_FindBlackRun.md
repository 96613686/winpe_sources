# FindBlackRun

- ea: `0x18000dfa0`
- end: `0x18000e0fe`
- name: `FindBlackRun`
- size: `350`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000214c`
- `0x180002600`
- `0x18000373c`
- `0x180003b38`

## callees

- `0x180002b54`
- `0x18000dfa0`

## pseudocode

```c
__int64 __fastcall FindBlackRun(__int64 a1, int a2, int a3)
{
  __int64 v3; // rbp
  int v5; // edi
  unsigned __int64 v6; // r14
  _DWORD *v7; // rbx
  int v8; // ebp
  unsigned int v9; // esi
  __int64 v10; // rax

  v3 = a2;
  v5 = a3 - a2;
  if ( (unsigned int)Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( v5 > 0 )
    {
      v6 = a1 + v5 / 8 + 1 + ((int)v3 >> 3);
      v7 = (_DWORD *)((v3 >> 3) + a1);
      if ( (unsigned __int64)v7 <= v6 )
      {
LABEL_6:
        v8 = v3 & 7;
        if ( v8 )
        {
          v9 = 8 - v8;
          if ( *((unsigned __int8 *)qword_18006C320 + (unsigned __int8)(*(unsigned __int8 *)v7 << v8)) <= 8 - v8 )
            v9 = *((unsigned __int8 *)qword_18006C320 + (unsigned __int8)(*(unsigned __int8 *)v7 << v8));
          if ( (int)(v9 + v8) < 8 )
            return v9;
          v7 = (_DWORD *)((char *)v7 + 1);
          if ( (unsigned int)Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline() )
          {
            if ( (unsigned __int64)v7 > v6 )
              return v9;
          }
          v5 -= v9;
        }
        else
        {
          v9 = 0;
        }
        if ( (unsigned int)v5 < 0x40 )
          goto LABEL_33;
        while ( ((unsigned __int8)v7 & 3) != 0 )
        {
          v10 = *(unsigned __int8 *)v7;
          if ( (_BYTE)v10 != 0xFF )
            return v9 + *((unsigned __int8 *)qword_18006C320 + v10);
          v9 += 8;
          v7 = (_DWORD *)((char *)v7 + 1);
          if ( (unsigned int)Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline()
            && (unsigned __int64)v7 > v6 )
          {
            return v9;
          }
          v5 -= 8;
        }
        while ( (unsigned int)v5 >= 0x20 && *v7 == -1 )
        {
          ++v7;
          v9 += 32;
          if ( (unsigned int)Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline()
            && (unsigned __int64)v7 > v6 )
          {
            return v9;
          }
          v5 -= 32;
        }
LABEL_33:
        while ( v5 >= 8 )
        {
          v10 = *(unsigned __int8 *)v7;
          if ( (_BYTE)v10 != 0xFF )
            return v9 + *((unsigned __int8 *)qword_18006C320 + v10);
          v7 = (_DWORD *)((char *)v7 + 1);
          v9 += 8;
          if ( (unsigned int)Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline()
            && (unsigned __int64)v7 > v6 )
          {
            return v9;
          }
          v5 -= 8;
        }
        if ( v5 > 0 )
          v9 += *((unsigned __int8 *)qword_18006C320 + *(unsigned __int8 *)v7);
        return v9;
      }
    }
  }
  else if ( v5 > 0 )
  {
    v6 = 0;
    v7 = (_DWORD *)((v3 >> 3) + a1);
    goto LABEL_6;
  }
  return 0;
}

```

## disassembly

```asm
0x18000dfa0  push    rbx
0x18000dfa2  push    rbp
0x18000dfa3  push    rsi
0x18000dfa4  push    rdi
0x18000dfa5  push    r12
0x18000dfa7  push    r14
0x18000dfa9  sub     rsp, 28h
0x18000dfad  mov     edi, r8d
0x18000dfb0  movsxd  rbp, edx
0x18000dfb3  mov     rbx, rcx
0x18000dfb6  sub     edi, ebp
0x18000dfb8  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000dfbd  test    eax, eax
0x18000dfbf  jnz     short loc_18000DFD8
0x18000dfc1  test    edi, edi
0x18000dfc3  jle     loc_18000E0EE
0x18000dfc9  mov     rax, rbp
0x18000dfcc  xor     r14d, r14d
0x18000dfcf  sar     rax, 3
0x18000dfd3  add     rbx, rax
0x18000dfd6  jmp     short loc_18000E012
0x18000dfd8  test    edi, edi
0x18000dfda  jle     loc_18000E0EE
0x18000dfe0  mov     eax, edi
0x18000dfe2  cdq
0x18000dfe3  and     edx, 7
0x18000dfe6  add     eax, edx
0x18000dfe8  sar     eax, 3
0x18000dfeb  inc     eax
0x18000dfed  movsxd  rdx, eax
0x18000dff0  mov     eax, ebp
0x18000dff2  sar     eax, 3
0x18000dff5  movsxd  r14, eax
0x18000dff8  lea     rax, [rbx+rdx]
0x18000dffc  add     r14, rax
0x18000dfff  mov     rax, rbp
0x18000e002  sar     rax, 3
0x18000e006  add     rbx, rax
0x18000e009  cmp     rbx, r14
0x18000e00c  ja      loc_18000E0EE
0x18000e012  lea     r12, qword_18006C320
0x18000e019  and     ebp, 7
0x18000e01c  jz      short loc_18000E05E
0x18000e01e  movzx   eax, byte ptr [rbx]
0x18000e021  mov     ecx, ebp
0x18000e023  shl     eax, cl
0x18000e025  mov     esi, 8
0x18000e02a  sub     esi, ebp
0x18000e02c  movzx   eax, al
0x18000e02f  movzx   ecx, byte ptr [rax+r12]
0x18000e034  cmp     ecx, esi
0x18000e036  cmovle  esi, ecx
0x18000e039  lea     eax, [rsi+rbp]
0x18000e03c  cmp     eax, 8
0x18000e03f  jl      loc_18000E0EA
0x18000e045  inc     rbx
0x18000e048  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000e04d  test    eax, eax
0x18000e04f  jz      short loc_18000E05A
0x18000e051  cmp     rbx, r14
0x18000e054  ja      loc_18000E0EA
0x18000e05a  sub     edi, esi
0x18000e05c  jmp     short loc_18000E060
0x18000e05e  xor     esi, esi
0x18000e060  cmp     edi, 40h ; '@'
0x18000e063  jb      short loc_18000E0D7
0x18000e065  jmp     short loc_18000E085
0x18000e067  movzx   eax, byte ptr [rbx]
0x18000e06a  cmp     al, 0FFh
0x18000e06c  jnz     short loc_18000E08C
0x18000e06e  add     esi, 8
0x18000e071  inc     rbx
0x18000e074  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000e079  test    eax, eax
0x18000e07b  jz      short loc_18000E082
0x18000e07d  cmp     rbx, r14
0x18000e080  ja      short loc_18000E0EA
0x18000e082  sub     edi, 8
0x18000e085  test    bl, 3
0x18000e088  jnz     short loc_18000E067
0x18000e08a  jmp     short loc_18000E0B2
0x18000e08c  movzx   eax, byte ptr [rax+r12]
0x18000e091  add     eax, esi
0x18000e093  jmp     short loc_18000E0F0
0x18000e095  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000e098  jnz     short loc_18000E0D7
0x18000e09a  add     rbx, 4
0x18000e09e  add     esi, 20h ; ' '
0x18000e0a1  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000e0a6  test    eax, eax
0x18000e0a8  jz      short loc_18000E0AF
0x18000e0aa  cmp     rbx, r14
0x18000e0ad  ja      short loc_18000E0EA
0x18000e0af  sub     edi, 20h ; ' '
0x18000e0b2  cmp     edi, 20h ; ' '
0x18000e0b5  jnb     short loc_18000E095
0x18000e0b7  jmp     short loc_18000E0D7
0x18000e0b9  movzx   eax, byte ptr [rbx]
0x18000e0bc  cmp     al, 0FFh
0x18000e0be  jnz     short loc_18000E08C
0x18000e0c0  inc     rbx
0x18000e0c3  add     esi, 8
0x18000e0c6  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000e0cb  test    eax, eax
0x18000e0cd  jz      short loc_18000E0D4
0x18000e0cf  cmp     rbx, r14
0x18000e0d2  ja      short loc_18000E0EA
0x18000e0d4  sub     edi, 8
0x18000e0d7  cmp     edi, 8
0x18000e0da  jge     short loc_18000E0B9
0x18000e0dc  test    edi, edi
0x18000e0de  jle     short loc_18000E0EA
0x18000e0e0  movzx   eax, byte ptr [rbx]
0x18000e0e3  movzx   eax, byte ptr [rax+r12]
0x18000e0e8  add     esi, eax
0x18000e0ea  mov     eax, esi
0x18000e0ec  jmp     short loc_18000E0F0
0x18000e0ee  xor     eax, eax
0x18000e0f0  add     rsp, 28h
0x18000e0f4  pop     r14
0x18000e0f6  pop     r12
0x18000e0f8  pop     rdi
0x18000e0f9  pop     rsi
0x18000e0fa  pop     rbp
0x18000e0fb  pop     rbx
0x18000e0fc  retn
```
