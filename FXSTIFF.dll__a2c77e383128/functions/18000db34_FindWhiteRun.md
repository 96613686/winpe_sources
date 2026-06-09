# FindWhiteRun

- ea: `0x18000db34`
- end: `0x18000dc91`
- name: `FindWhiteRun`
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
- `0x18000db34`

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
          if ( *((unsigned __int8 *)qword_18006C400 + (unsigned __int8)(*(unsigned __int8 *)v7 << v8)) <= 8 - v8 )
            v9 = *((unsigned __int8 *)qword_18006C400 + (unsigned __int8)(*(unsigned __int8 *)v7 << v8));
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
            return v9 + *((unsigned __int8 *)qword_18006C400 + v10);
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
            return v9 + *((unsigned __int8 *)qword_18006C400 + v10);
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
          v9 += *((unsigned __int8 *)qword_18006C400 + *(unsigned __int8 *)v7);
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
0x18000db34  push    rbx
0x18000db36  push    rbp
0x18000db37  push    rsi
0x18000db38  push    rdi
0x18000db39  push    r12
0x18000db3b  push    r14
0x18000db3d  sub     rsp, 28h
0x18000db41  mov     edi, r8d
0x18000db44  movsxd  rbp, edx
0x18000db47  mov     rbx, rcx
0x18000db4a  sub     edi, ebp
0x18000db4c  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000db51  test    eax, eax
0x18000db53  jnz     short loc_18000DB6C
0x18000db55  test    edi, edi
0x18000db57  jle     loc_18000DC82
0x18000db5d  mov     rax, rbp
0x18000db60  xor     r14d, r14d
0x18000db63  sar     rax, 3
0x18000db67  add     rbx, rax
0x18000db6a  jmp     short loc_18000DBA6
0x18000db6c  test    edi, edi
0x18000db6e  jle     loc_18000DC82
0x18000db74  mov     eax, edi
0x18000db76  cdq
0x18000db77  and     edx, 7
0x18000db7a  add     eax, edx
0x18000db7c  sar     eax, 3
0x18000db7f  inc     eax
0x18000db81  movsxd  rdx, eax
0x18000db84  mov     eax, ebp
0x18000db86  sar     eax, 3
0x18000db89  movsxd  r14, eax
0x18000db8c  lea     rax, [rbx+rdx]
0x18000db90  add     r14, rax
0x18000db93  mov     rax, rbp
0x18000db96  sar     rax, 3
0x18000db9a  add     rbx, rax
0x18000db9d  cmp     rbx, r14
0x18000dba0  ja      loc_18000DC82
0x18000dba6  lea     r12, qword_18006C400
0x18000dbad  and     ebp, 7
0x18000dbb0  jz      short loc_18000DBF2
0x18000dbb2  movzx   eax, byte ptr [rbx]
0x18000dbb5  mov     ecx, ebp
0x18000dbb7  shl     eax, cl
0x18000dbb9  mov     esi, 8
0x18000dbbe  sub     esi, ebp
0x18000dbc0  movzx   eax, al
0x18000dbc3  movzx   ecx, byte ptr [rax+r12]
0x18000dbc8  cmp     ecx, esi
0x18000dbca  cmovle  esi, ecx
0x18000dbcd  lea     eax, [rsi+rbp]
0x18000dbd0  cmp     eax, 8
0x18000dbd3  jl      loc_18000DC7E
0x18000dbd9  inc     rbx
0x18000dbdc  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000dbe1  test    eax, eax
0x18000dbe3  jz      short loc_18000DBEE
0x18000dbe5  cmp     rbx, r14
0x18000dbe8  ja      loc_18000DC7E
0x18000dbee  sub     edi, esi
0x18000dbf0  jmp     short loc_18000DBF4
0x18000dbf2  xor     esi, esi
0x18000dbf4  cmp     edi, 40h ; '@'
0x18000dbf7  jb      short loc_18000DC6B
0x18000dbf9  jmp     short loc_18000DC19
0x18000dbfb  movzx   eax, byte ptr [rbx]
0x18000dbfe  test    al, al
0x18000dc00  jnz     short loc_18000DC20
0x18000dc02  add     esi, 8
0x18000dc05  inc     rbx
0x18000dc08  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000dc0d  test    eax, eax
0x18000dc0f  jz      short loc_18000DC16
0x18000dc11  cmp     rbx, r14
0x18000dc14  ja      short loc_18000DC7E
0x18000dc16  sub     edi, 8
0x18000dc19  test    bl, 3
0x18000dc1c  jnz     short loc_18000DBFB
0x18000dc1e  jmp     short loc_18000DC46
0x18000dc20  movzx   eax, byte ptr [rax+r12]
0x18000dc25  add     eax, esi
0x18000dc27  jmp     short loc_18000DC84
0x18000dc29  cmp     dword ptr [rbx], 0
0x18000dc2c  jnz     short loc_18000DC6B
0x18000dc2e  add     rbx, 4
0x18000dc32  add     esi, 20h ; ' '
0x18000dc35  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000dc3a  test    eax, eax
0x18000dc3c  jz      short loc_18000DC43
0x18000dc3e  cmp     rbx, r14
0x18000dc41  ja      short loc_18000DC7E
0x18000dc43  sub     edi, 20h ; ' '
0x18000dc46  cmp     edi, 20h ; ' '
0x18000dc49  jnb     short loc_18000DC29
0x18000dc4b  jmp     short loc_18000DC6B
0x18000dc4d  movzx   eax, byte ptr [rbx]
0x18000dc50  test    al, al
0x18000dc52  jnz     short loc_18000DC20
0x18000dc54  inc     rbx
0x18000dc57  add     esi, 8
0x18000dc5a  call    Feature_Print_PlatformStabilizationFixes_2026_Wave1__private_IsEnabledDeviceUsageNoInline
0x18000dc5f  test    eax, eax
0x18000dc61  jz      short loc_18000DC68
0x18000dc63  cmp     rbx, r14
0x18000dc66  ja      short loc_18000DC7E
0x18000dc68  sub     edi, 8
0x18000dc6b  cmp     edi, 8
0x18000dc6e  jge     short loc_18000DC4D
0x18000dc70  test    edi, edi
0x18000dc72  jle     short loc_18000DC7E
0x18000dc74  movzx   eax, byte ptr [rbx]
0x18000dc77  movzx   eax, byte ptr [rax+r12]
0x18000dc7c  add     esi, eax
0x18000dc7e  mov     eax, esi
0x18000dc80  jmp     short loc_18000DC84
0x18000dc82  xor     eax, eax
0x18000dc84  add     rsp, 28h
0x18000dc88  pop     r14
0x18000dc8a  pop     r12
0x18000dc8c  pop     rdi
0x18000dc8d  pop     rsi
0x18000dc8e  pop     rbp
0x18000dc8f  pop     rbx
0x18000dc90  retn
```
