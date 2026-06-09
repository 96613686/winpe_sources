# VfsProcessDeletePackageDirectory

- ea: `0x140006064`
- end: `0x1400060fd`
- name: `VfsProcessDeletePackageDirectory`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140005c50`

## callees

- `0x140006064`
- `0x1400061b4`
- `0x14000aefc`
- `0x140012acc`

## string_xrefs

- `0x1400060b1`: `VfsProcessDeletePackageDirectory() - Failed to check directory empty. Status: 0x%08X`
- `0x1400060e4`: `VfsProcessDeletePackageDirectory() - Failed to delay copy file. Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsProcessDeletePackageDirectory(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  char v10; // [rsp+60h] [rbp+8h] BYREF

  v3 = a3;
  if ( !**(_BYTE **)(*(_QWORD *)(a1 + 16) + 56LL) )
    return 0;
  v10 = 0;
  LOBYTE(a3) = 1;
  v7 = VfsCheckDirectoryEmpty(a1, v3, a3, &v10);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( v10 )
    {
      v9 = VfsDelayedCopy(a1, a2, v3);
      v8 = v9;
      if ( v9 < 0 )
        LogWrite(
          1,
          0,
          L"VfsProcessDeletePackageDirectory() - Failed to delay copy file. Status: 0x%08X",
          (unsigned int)v9,
          v9);
    }
    else
    {
      return (unsigned int)-1073741567;
    }
  }
  else
  {
    LogWrite(
      1,
      0,
      L"VfsProcessDeletePackageDirectory() - Failed to check directory empty. Status: 0x%08X",
      (unsigned int)v7,
      v7);
  }
  return v8;
}

```

## disassembly

```asm
0x140006064  push    rbx
0x140006066  push    rsi
0x140006067  push    rdi
0x140006068  push    r14
0x14000606a  sub     rsp, 38h
0x14000606e  mov     rsi, r8
0x140006071  mov     r14, rdx
0x140006074  mov     rdi, rcx
0x140006077  mov     rax, [rcx+10h]
0x14000607b  mov     r9, [rax+38h]
0x14000607f  cmp     byte ptr [r9], 0
0x140006083  jnz     short loc_140006092
0x140006085  xor     eax, eax
0x140006087  add     rsp, 38h
0x14000608b  pop     r14
0x14000608d  pop     rdi
0x14000608e  pop     rsi
0x14000608f  pop     rbx
0x140006090  retn
0x140006092  mov     [rsp+58h+arg_0], 0
0x140006097  lea     r9, [rsp+58h+arg_0]
0x14000609c  mov     r8b, 1
0x14000609f  mov     rdx, rsi
0x1400060a2  call    VfsCheckDirectoryEmpty
0x1400060a7  mov     ebx, eax
0x1400060a9  mov     [rsp+58h+var_38], eax
0x1400060ad  test    eax, eax
0x1400060af  jns     short loc_1400060BA
0x1400060b1  lea     r8, aVfsprocessdele_0; "VfsProcessDeletePackageDirectory() - Fa"...
0x1400060b8  jmp     short loc_1400060EB
0x1400060ba  cmp     [rsp+58h+arg_0], 0
0x1400060bf  jnz     short loc_1400060CC
0x1400060c1  mov     ebx, 0C0000101h
0x1400060c6  mov     [rsp+58h+var_38], ebx
0x1400060ca  jmp     short loc_1400060F9
0x1400060cc  mov     r8, rsi
0x1400060cf  mov     rdx, r14
0x1400060d2  mov     rcx, rdi
0x1400060d5  call    VfsDelayedCopy
0x1400060da  mov     ebx, eax
0x1400060dc  mov     [rsp+58h+var_38], eax
0x1400060e0  test    eax, eax
0x1400060e2  jns     short loc_1400060F9
0x1400060e4  lea     r8, aVfsprocessdele_3; "VfsProcessDeletePackageDirectory() - Fa"...
0x1400060eb  mov     r9d, eax
0x1400060ee  xor     edx, edx
0x1400060f0  lea     ecx, [rdx+1]
0x1400060f3  call    LogWrite
0x1400060f8  nop
0x1400060f9  mov     eax, ebx
0x1400060fb  jmp     short loc_140006087
0x140014a6f  push    rbp
0x140014a71  sub     rsp, 20h
0x140014a75  mov     rbp, rdx
0x140014a78  add     rsp, 20h
0x140014a7c  pop     rbp
0x140014a7d  retn
```
