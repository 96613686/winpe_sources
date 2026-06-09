# write_text_utf8_nolock(int,char const * const,uint)

- ea: `0x14002158c`
- end: `0x140021700`
- name: `?write_text_utf8_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDI@Z`
- size: `372`
- prototype: `__int64 __fastcall(__int64, int, __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400218b8`

## callees

- `0x14000a640`
- `0x14001dca4`
- `0x14002158c`
- `0x140025090`

## import_xrefs

- `KERNEL32!WriteFile` at `0x1400216a4`
- `KERNEL32!WriteFile` at `0x1400216a4`
- `KERNEL32!GetLastError` at `0x1400216c9`
- `KERNEL32!GetLastError` at `0x1400216c9`

## pseudocode

```c
__int64 __fastcall write_text_utf8_nolock(__int64 a1, int a2, __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // r14
  int v6; // r15d
  __int16 *v7; // rdi
  void *v8; // r12
  char *v9; // r9
  __int16 v10; // ax
  unsigned int v11; // ebp
  unsigned int v12; // esi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-1458h] BYREF
  _BYTE v15[1704]; // [rsp+50h] [rbp-1448h] BYREF
  char v16; // [rsp+6F8h] [rbp-DA0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+700h] [rbp-D98h] BYREF

  v5 = (unsigned __int64)a3 + a4;
  v6 = (int)a3;
  v7 = a3;
  v8 = *(void **)(qword_14003E600[(__int64)a2 >> 6] + 72LL * (a2 & 0x3F) + 40);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)a3 < v5 )
  {
LABEL_2:
    v9 = v15;
    do
    {
      if ( (unsigned __int64)v7 >= v5 )
        break;
      v10 = *v7++;
      if ( v10 == 10 )
      {
        *(_WORD *)v9 = 13;
        v9 += 2;
      }
      *(_WORD *)v9 = v10;
      v9 += 2;
    }
    while ( v9 < &v16 );
    v11 = _acrt_WideCharToMultiByte(65001, 0, (unsigned int)v15, (v9 - v15) >> 1, (unsigned int)&Overlapped, 3413, 0, 0);
    if ( v11 )
    {
      v12 = 0;
      while ( 1 )
      {
        NumberOfBytesWritten = 0;
        if ( !WriteFile(v8, (char *)&Overlapped + v12, v11 - v12, &NumberOfBytesWritten, 0) )
          break;
        v12 += NumberOfBytesWritten;
        if ( v12 >= v11 )
        {
          *(_DWORD *)(a1 + 4) = (_DWORD)v7 - v6;
          if ( (unsigned __int64)v7 < v5 )
            goto LABEL_2;
          return a1;
        }
      }
    }
    *(_DWORD *)a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x14002158c  mov     [rsp+arg_0], rbx
0x140021591  mov     [rsp+arg_10], rbp
0x140021596  push    rsi
0x140021597  push    rdi
0x140021598  push    r12
0x14002159a  push    r14
0x14002159c  push    r15
0x14002159e  mov     eax, 1470h
0x1400215a3  call    __alloca_probe
0x1400215a8  sub     rsp, rax
0x1400215ab  mov     rax, cs:__security_cookie
0x1400215b2  xor     rax, rsp
0x1400215b5  mov     [rsp+1498h+var_38], rax
0x1400215bd  movsxd  r10, edx
0x1400215c0  mov     rbx, rcx
0x1400215c3  mov     rax, r10
0x1400215c6  mov     r14d, r9d
0x1400215c9  sar     rax, 6
0x1400215cd  lea     rcx, qword_14003E600
0x1400215d4  and     r10d, 3Fh
0x1400215d8  add     r14, r8
0x1400215db  mov     r15, r8
0x1400215de  mov     rdi, r8
0x1400215e1  mov     rax, [rcx+rax*8]
0x1400215e5  lea     rdx, [r10+r10*8]
0x1400215e9  mov     r12, [rax+rdx*8+28h]
0x1400215ee  xor     eax, eax
0x1400215f0  mov     [rbx], rax
0x1400215f3  mov     [rbx+8], eax
0x1400215f6  cmp     r8, r14
0x1400215f9  jnb     loc_1400216D1
0x1400215ff  lea     r9, [rsp+1498h+var_1448]
0x140021604  cmp     rdi, r14
0x140021607  jnb     short loc_140021635
0x140021609  movzx   eax, word ptr [rdi]
0x14002160c  add     rdi, 2
0x140021610  cmp     ax, 0Ah
0x140021614  jnz     short loc_140021620
0x140021616  mov     word ptr [r9], 0Dh
0x14002161c  add     r9, 2
0x140021620  mov     [r9], ax
0x140021624  add     r9, 2
0x140021628  lea     rax, [rsp+1498h+var_DA0]
0x140021630  cmp     r9, rax
0x140021633  jb      short loc_140021604
0x140021635  and     [rsp+1498h+var_1460], 0
0x14002163b  lea     rax, [rsp+1498h+var_1448]
0x140021640  and     [rsp+1498h+var_1468], 0
0x140021646  lea     r8, [rsp+1498h+var_1448]
0x14002164b  sub     r9, rax
0x14002164e  mov     [rsp+1498h+var_1470], 0D55h
0x140021656  lea     rax, [rsp+1498h+Overlapped]
0x14002165e  sar     r9, 1
0x140021661  xor     edx, edx
0x140021663  mov     [rsp+1498h+lpOverlapped], rax; lpOverlapped
0x140021668  mov     ecx, 0FDE9h
0x14002166d  call    __acrt_WideCharToMultiByte
0x140021672  mov     ebp, eax
0x140021674  test    eax, eax
0x140021676  jz      short loc_1400216C9
0x140021678  xor     esi, esi
0x14002167a  test    eax, eax
0x14002167c  jz      short loc_1400216B6
0x14002167e  and     [rsp+1498h+NumberOfBytesWritten], 0
0x140021683  lea     rdx, [rsp+1498h+Overlapped]
0x14002168b  and     [rsp+1498h+lpOverlapped], 0
0x140021691  lea     r9, [rsp+1498h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140021696  mov     ecx, esi
0x140021698  mov     r8d, ebp
0x14002169b  add     rdx, rcx; lpBuffer
0x14002169e  sub     r8d, esi; nNumberOfBytesToWrite
0x1400216a1  mov     rcx, r12; hFile
0x1400216a4  call    cs:WriteFile
0x1400216aa  test    eax, eax
0x1400216ac  jz      short loc_1400216C9
0x1400216ae  add     esi, [rsp+1498h+NumberOfBytesWritten]
0x1400216b2  cmp     esi, ebp
0x1400216b4  jb      short loc_14002167E
0x1400216b6  mov     eax, edi
0x1400216b8  sub     eax, r15d
0x1400216bb  mov     [rbx+4], eax
0x1400216be  cmp     rdi, r14
0x1400216c1  jb      loc_1400215FF
0x1400216c7  jmp     short loc_1400216D1
0x1400216c9  call    cs:GetLastError
0x1400216cf  mov     [rbx], eax
0x1400216d1  mov     rax, rbx
0x1400216d4  mov     rcx, [rsp+1498h+var_38]
0x1400216dc  xor     rcx, rsp; StackCookie
0x1400216df  call    __security_check_cookie
0x1400216e4  lea     r11, [rsp+1498h+var_28]
0x1400216ec  mov     rbx, [r11+30h]
0x1400216f0  mov     rbp, [r11+40h]
0x1400216f4  mov     rsp, r11
0x1400216f7  pop     r15
0x1400216f9  pop     r14
0x1400216fb  pop     r12
0x1400216fd  pop     rdi
0x1400216fe  pop     rsi
0x1400216ff  retn
```
