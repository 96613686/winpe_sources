# FindBlackRun

- ea: `0x18000d9d0`
- end: `0x18000db2d`
- name: `FindBlackRun`
- size: `349`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000212c`
- `0x1800025e0`
- `0x180003704`
- `0x180003b00`

## callees

- `0x180002b30`
- `0x18000d9d0`

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
          if ( *((unsigned __int8 *)qword_18006C2F0 + (unsigned __int8)(*(unsigned __int8 *)v7 << v8)) <= 8 - v8 )
            v9 = *((unsigned __int8 *)qword_18006C2F0 + (unsigned __int8)(*(unsigned __int8 *)v7 << v8));
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
            return v9 + *((unsigned __int8 *)qword_18006C2F0 + v10);
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
            return v9 + *((unsigned __int8 *)qword_18006C2F0 + v10);
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
          v9 += *((unsigned __int8 *)qword_18006C2F0 + *(unsigned __int8 *)v7);
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
0x18000d9d0  push    rbx
0x18000d9d2  push    rbp
0x18000d9d3  push    rsi
0x18000d9d4  push    rdi
0x18000d9d5  push    r12
0x18000d9d7  push    r14
0x18000d9d9  sub     rsp, 28h
0x18000d9dd  mov     edi, r8d
0x18000d9e0  movsxd  rbp, edx
0x18000d9e3  mov     rbx, rcx
0x18000d9e6  sub     edi, ebp
0x18000d9e8  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000d9ed  test    eax, eax
0x18000d9ef  jnz     short loc_18000DA08
0x18000d9f1  test    edi, edi
0x18000d9f3  jle     loc_18000DB1E
0x18000d9f9  mov     rax, rbp
0x18000d9fc  xor     r14d, r14d
0x18000d9ff  sar     rax, 3
0x18000da03  add     rbx, rax
0x18000da06  jmp     short loc_18000DA42
0x18000da08  test    edi, edi
0x18000da0a  jle     loc_18000DB1E
0x18000da10  mov     eax, edi
0x18000da12  cdq
0x18000da13  and     edx, 7
0x18000da16  add     eax, edx
0x18000da18  sar     eax, 3
0x18000da1b  inc     eax
0x18000da1d  movsxd  rdx, eax
0x18000da20  mov     eax, ebp
0x18000da22  sar     eax, 3
0x18000da25  movsxd  r14, eax
0x18000da28  lea     rax, [rbx+rdx]
0x18000da2c  add     r14, rax
0x18000da2f  mov     rax, rbp
0x18000da32  sar     rax, 3
0x18000da36  add     rbx, rax
0x18000da39  cmp     rbx, r14
0x18000da3c  ja      loc_18000DB1E
0x18000da42  lea     r12, qword_18006C2F0
0x18000da49  and     ebp, 7
0x18000da4c  jz      short loc_18000DA8E
0x18000da4e  movzx   eax, byte ptr [rbx]
0x18000da51  mov     ecx, ebp
0x18000da53  shl     eax, cl
0x18000da55  mov     esi, 8
0x18000da5a  sub     esi, ebp
0x18000da5c  movzx   eax, al
0x18000da5f  movzx   ecx, byte ptr [rax+r12]
0x18000da64  cmp     ecx, esi
0x18000da66  cmovle  esi, ecx
0x18000da69  lea     eax, [rsi+rbp]
0x18000da6c  cmp     eax, 8
0x18000da6f  jl      loc_18000DB1A
0x18000da75  inc     rbx
0x18000da78  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000da7d  test    eax, eax
0x18000da7f  jz      short loc_18000DA8A
0x18000da81  cmp     rbx, r14
0x18000da84  ja      loc_18000DB1A
0x18000da8a  sub     edi, esi
0x18000da8c  jmp     short loc_18000DA90
0x18000da8e  xor     esi, esi
0x18000da90  cmp     edi, 40h ; '@'
0x18000da93  jb      short loc_18000DB07
0x18000da95  jmp     short loc_18000DAB5
0x18000da97  movzx   eax, byte ptr [rbx]
0x18000da9a  cmp     al, 0FFh
0x18000da9c  jnz     short loc_18000DABC
0x18000da9e  add     esi, 8
0x18000daa1  inc     rbx
0x18000daa4  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000daa9  test    eax, eax
0x18000daab  jz      short loc_18000DAB2
0x18000daad  cmp     rbx, r14
0x18000dab0  ja      short loc_18000DB1A
0x18000dab2  sub     edi, 8
0x18000dab5  test    bl, 3
0x18000dab8  jnz     short loc_18000DA97
0x18000daba  jmp     short loc_18000DAE2
0x18000dabc  movzx   eax, byte ptr [rax+r12]
0x18000dac1  add     eax, esi
0x18000dac3  jmp     short loc_18000DB20
0x18000dac5  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000dac8  jnz     short loc_18000DB07
0x18000daca  add     rbx, 4
0x18000dace  add     esi, 20h ; ' '
0x18000dad1  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000dad6  test    eax, eax
0x18000dad8  jz      short loc_18000DADF
0x18000dada  cmp     rbx, r14
0x18000dadd  ja      short loc_18000DB1A
0x18000dadf  sub     edi, 20h ; ' '
0x18000dae2  cmp     edi, 20h ; ' '
0x18000dae5  jnb     short loc_18000DAC5
0x18000dae7  jmp     short loc_18000DB07
0x18000dae9  movzx   eax, byte ptr [rbx]
0x18000daec  cmp     al, 0FFh
0x18000daee  jnz     short loc_18000DABC
0x18000daf0  inc     rbx
0x18000daf3  add     esi, 8
0x18000daf6  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000dafb  test    eax, eax
0x18000dafd  jz      short loc_18000DB04
0x18000daff  cmp     rbx, r14
0x18000db02  ja      short loc_18000DB1A
0x18000db04  sub     edi, 8
0x18000db07  cmp     edi, 8
0x18000db0a  jge     short loc_18000DAE9
0x18000db0c  test    edi, edi
0x18000db0e  jle     short loc_18000DB1A
0x18000db10  movzx   eax, byte ptr [rbx]
0x18000db13  movzx   eax, byte ptr [rax+r12]
0x18000db18  add     esi, eax
0x18000db1a  mov     eax, esi
0x18000db1c  jmp     short loc_18000DB20
0x18000db1e  xor     eax, eax
0x18000db20  add     rsp, 28h
0x18000db24  pop     r14
0x18000db26  pop     r12
0x18000db28  pop     rdi
0x18000db29  pop     rsi
0x18000db2a  pop     rbp
0x18000db2b  pop     rbx
0x18000db2c  retn
```
