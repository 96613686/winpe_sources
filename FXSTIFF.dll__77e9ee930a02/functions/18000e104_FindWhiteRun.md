# FindWhiteRun

- ea: `0x18000e104`
- end: `0x18000e262`
- name: `FindWhiteRun`
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
- `0x18000e104`

## pseudocode

```c
__int64 __fastcall FindWhiteRun(__int64 a1, int a2, int a3)
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
          if ( *((unsigned __int8 *)qword_18006C430 + (unsigned __int8)(*(unsigned __int8 *)v7 << v8)) <= 8 - v8 )
            v9 = *((unsigned __int8 *)qword_18006C430 + (unsigned __int8)(*(unsigned __int8 *)v7 << v8));
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
          if ( (_BYTE)v10 )
            return v9 + *((unsigned __int8 *)qword_18006C430 + v10);
          v9 += 8;
          v7 = (_DWORD *)((char *)v7 + 1);
          if ( (unsigned int)Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline()
            && (unsigned __int64)v7 > v6 )
          {
            return v9;
          }
          v5 -= 8;
        }
        while ( (unsigned int)v5 >= 0x20 && !*v7 )
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
          if ( (_BYTE)v10 )
            return v9 + *((unsigned __int8 *)qword_18006C430 + v10);
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
          v9 += *((unsigned __int8 *)qword_18006C430 + *(unsigned __int8 *)v7);
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
0x18000e104  push    rbx
0x18000e106  push    rbp
0x18000e107  push    rsi
0x18000e108  push    rdi
0x18000e109  push    r12
0x18000e10b  push    r14
0x18000e10d  sub     rsp, 28h
0x18000e111  mov     edi, r8d
0x18000e114  movsxd  rbp, edx
0x18000e117  mov     rbx, rcx
0x18000e11a  sub     edi, ebp
0x18000e11c  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000e121  test    eax, eax
0x18000e123  jnz     short loc_18000E13C
0x18000e125  test    edi, edi
0x18000e127  jle     loc_18000E252
0x18000e12d  mov     rax, rbp
0x18000e130  xor     r14d, r14d
0x18000e133  sar     rax, 3
0x18000e137  add     rbx, rax
0x18000e13a  jmp     short loc_18000E176
0x18000e13c  test    edi, edi
0x18000e13e  jle     loc_18000E252
0x18000e144  mov     eax, edi
0x18000e146  cdq
0x18000e147  and     edx, 7
0x18000e14a  add     eax, edx
0x18000e14c  sar     eax, 3
0x18000e14f  inc     eax
0x18000e151  movsxd  rdx, eax
0x18000e154  mov     eax, ebp
0x18000e156  sar     eax, 3
0x18000e159  movsxd  r14, eax
0x18000e15c  lea     rax, [rbx+rdx]
0x18000e160  add     r14, rax
0x18000e163  mov     rax, rbp
0x18000e166  sar     rax, 3
0x18000e16a  add     rbx, rax
0x18000e16d  cmp     rbx, r14
0x18000e170  ja      loc_18000E252
0x18000e176  lea     r12, qword_18006C430
0x18000e17d  and     ebp, 7
0x18000e180  jz      short loc_18000E1C2
0x18000e182  movzx   eax, byte ptr [rbx]
0x18000e185  mov     ecx, ebp
0x18000e187  shl     eax, cl
0x18000e189  mov     esi, 8
0x18000e18e  sub     esi, ebp
0x18000e190  movzx   eax, al
0x18000e193  movzx   ecx, byte ptr [rax+r12]
0x18000e198  cmp     ecx, esi
0x18000e19a  cmovle  esi, ecx
0x18000e19d  lea     eax, [rsi+rbp]
0x18000e1a0  cmp     eax, 8
0x18000e1a3  jl      loc_18000E24E
0x18000e1a9  inc     rbx
0x18000e1ac  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000e1b1  test    eax, eax
0x18000e1b3  jz      short loc_18000E1BE
0x18000e1b5  cmp     rbx, r14
0x18000e1b8  ja      loc_18000E24E
0x18000e1be  sub     edi, esi
0x18000e1c0  jmp     short loc_18000E1C4
0x18000e1c2  xor     esi, esi
0x18000e1c4  cmp     edi, 40h ; '@'
0x18000e1c7  jb      short loc_18000E23B
0x18000e1c9  jmp     short loc_18000E1E9
0x18000e1cb  movzx   eax, byte ptr [rbx]
0x18000e1ce  test    al, al
0x18000e1d0  jnz     short loc_18000E1F0
0x18000e1d2  add     esi, 8
0x18000e1d5  inc     rbx
0x18000e1d8  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000e1dd  test    eax, eax
0x18000e1df  jz      short loc_18000E1E6
0x18000e1e1  cmp     rbx, r14
0x18000e1e4  ja      short loc_18000E24E
0x18000e1e6  sub     edi, 8
0x18000e1e9  test    bl, 3
0x18000e1ec  jnz     short loc_18000E1CB
0x18000e1ee  jmp     short loc_18000E216
0x18000e1f0  movzx   eax, byte ptr [rax+r12]
0x18000e1f5  add     eax, esi
0x18000e1f7  jmp     short loc_18000E254
0x18000e1f9  cmp     dword ptr [rbx], 0
0x18000e1fc  jnz     short loc_18000E23B
0x18000e1fe  add     rbx, 4
0x18000e202  add     esi, 20h ; ' '
0x18000e205  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000e20a  test    eax, eax
0x18000e20c  jz      short loc_18000E213
0x18000e20e  cmp     rbx, r14
0x18000e211  ja      short loc_18000E24E
0x18000e213  sub     edi, 20h ; ' '
0x18000e216  cmp     edi, 20h ; ' '
0x18000e219  jnb     short loc_18000E1F9
0x18000e21b  jmp     short loc_18000E23B
0x18000e21d  movzx   eax, byte ptr [rbx]
0x18000e220  test    al, al
0x18000e222  jnz     short loc_18000E1F0
0x18000e224  inc     rbx
0x18000e227  add     esi, 8
0x18000e22a  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000e22f  test    eax, eax
0x18000e231  jz      short loc_18000E238
0x18000e233  cmp     rbx, r14
0x18000e236  ja      short loc_18000E24E
0x18000e238  sub     edi, 8
0x18000e23b  cmp     edi, 8
0x18000e23e  jge     short loc_18000E21D
0x18000e240  test    edi, edi
0x18000e242  jle     short loc_18000E24E
0x18000e244  movzx   eax, byte ptr [rbx]
0x18000e247  movzx   eax, byte ptr [rax+r12]
0x18000e24c  add     esi, eax
0x18000e24e  mov     eax, esi
0x18000e250  jmp     short loc_18000E254
0x18000e252  xor     eax, eax
0x18000e254  add     rsp, 28h
0x18000e258  pop     r14
0x18000e25a  pop     r12
0x18000e25c  pop     rdi
0x18000e25d  pop     rsi
0x18000e25e  pop     rbp
0x18000e25f  pop     rbx
0x18000e260  retn
```
