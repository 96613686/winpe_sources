# DwCountSynthFeatures

- ea: `0x180071e98`
- end: `0x1800720b5`
- name: `DwCountSynthFeatures`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180047f54`

## callees

- `0x180007220`
- `0x18003f288`
- `0x180071d30`
- `0x180071e98`
- `0x180075010`

## string_xrefs

- `0x180071f72`: `DwCountSynthFeatures: Unable to create synthesized feature for installable Feature index %d.`
- `0x180071fac`: `Internal error:  DwCountSynthFeatures - atrOptInstallable should never be branchless.`
- `0x180072039`: `DwCountSynthFeatures: Unable to create synthesized feature for installable option: fea=%d, opt=%d.`

## pseudocode

```c
__int64 __fastcall DwCountSynthFeatures(unsigned int (__fastcall *a1)(_QWORD, __int64, _QWORD, __int64), __int64 a2)
{
  unsigned int v5; // ebp
  unsigned int v6; // r15d
  __int64 v7; // rsi
  __int64 v8; // r13
  __int64 v9; // rax
  __int64 v10; // r12
  __int64 v11; // r11
  int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // r14d
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // [rsp+30h] [rbp-48h]
  unsigned int v18; // [rsp+80h] [rbp+8h] BYREF
  unsigned int i; // [rsp+90h] [rbp+18h]
  unsigned int v20; // [rsp+98h] [rbp+20h]

  v18 = 0;
  if ( a1 && !*(_DWORD *)(a2 + 296) )
    return 0;
  v5 = 0;
  v6 = 0;
  v7 = *(_QWORD *)(a2 + 264);
  v17 = *(_QWORD *)(a2 + 72);
  v20 = *(_DWORD *)(a2 + 272);
  if ( v20 )
  {
    v8 = 0;
    do
    {
      if ( !a1 )
      {
        v9 = 396 * v8;
        *(_QWORD *)(v9 + v7 + 376) = -1;
        *(_DWORD *)(v9 + v7 + 372) = -1;
      }
      v10 = 396 * v8;
      if ( (unsigned int)BReadDataInGlobalNode(396 * v8 + v7 + 16, &v18, a2) && *(_DWORD *)(v18 + *(_QWORD *)a2) == 1 )
      {
        if ( a1 )
        {
          if ( !a1(v6, 0xFFFFFFFFLL, v5, a2) )
          {
            WriteDbgTraceErrorGpd(
              "DwCountSynthFeatures",
              "DwCountSynthFeatures: Unable to create synthesized feature for installable Feature index %d.",
              v6);
            *(_DWORD *)(v10 + v7 + 380) = -1;
          }
          v11 = v17;
        }
        ++v5;
      }
      v12 = *(_DWORD *)(v10 + v7 + 88);
      if ( v12 != 0x7FFFFFFF )
      {
        if ( v12 >= 0 )
        {
          v13 = *(_DWORD *)(v10 + v7 + 392);
          v14 = 0;
          for ( i = v13; v14 < v13; ++v14 )
          {
            v15 = *(unsigned int *)(v10 + v7 + 88);
            while ( 1 )
            {
              v16 = 5 * v15;
              if ( *(_DWORD *)(v11 + 20 * v15 + 4) == v14 )
                break;
              v15 = *(unsigned int *)(v11 + 20 * v15 + 8);
              if ( (_DWORD)v15 == -1 )
              {
                if ( *(_DWORD *)(v11 + 4 * v16 + 4) != -1 )
                  goto LABEL_30;
                break;
              }
            }
            if ( *(_DWORD *)(v11 + 4 * v16 + 16) == 1
              && *(_DWORD *)(*(unsigned int *)(v11 + 4 * v16 + 12) + *(_QWORD *)a2) == 1 )
            {
              if ( a1 )
              {
                if ( !a1(v6, v14, v5, a2) )
                {
                  WriteDbgTraceErrorGpd(
                    "DwCountSynthFeatures",
                    "DwCountSynthFeatures: Unable to create synthesized feature for installable option: fea=%d, opt=%d.",
                    v6,
                    v14);
                  *(_DWORD *)(v10 + v7 + 368) = 0x7FFFFFFF;
                }
                v11 = v17;
                v13 = i;
              }
              ++v5;
            }
LABEL_30:
            ;
          }
        }
        else
        {
          WriteDbgTraceErrorGpd(
            "DwCountSynthFeatures",
            "Internal error:  DwCountSynthFeatures - atrOptInstallable should never be branchless.");
        }
      }
      ++v6;
      ++v8;
    }
    while ( v6 < v20 );
  }
  if ( a1 )
    BEnableInvInstallableCombos(a2);
  return v5;
}

```

## disassembly

```asm
0x180071e98  mov     rax, rsp
0x180071e9b  mov     [rax+10h], rbx
0x180071e9f  push    rbp
0x180071ea0  push    rsi
0x180071ea1  push    rdi
0x180071ea2  push    r12
0x180071ea4  push    r13
0x180071ea6  push    r14
0x180071ea8  push    r15
0x180071eaa  sub     rsp, 40h
0x180071eae  mov     dword ptr [rax+8], 0
0x180071eb5  mov     rbx, rdx
0x180071eb8  mov     rdi, rcx
0x180071ebb  test    rcx, rcx
0x180071ebe  jz      short loc_180071ED0
0x180071ec0  cmp     dword ptr [rdx+128h], 0
0x180071ec7  jnz     short loc_180071ED0
0x180071ec9  xor     eax, eax
0x180071ecb  jmp     loc_18007209D
0x180071ed0  mov     eax, [rdx+110h]
0x180071ed6  xor     ebp, ebp
0x180071ed8  mov     r11, [rdx+48h]
0x180071edc  xor     r15d, r15d
0x180071edf  mov     rsi, [rdx+108h]
0x180071ee6  mov     [rsp+78h+var_48], r11
0x180071eeb  mov     [rsp+78h+arg_18], eax
0x180071ef2  test    eax, eax
0x180071ef4  jz      loc_18007208E
0x180071efa  xor     r13d, r13d
0x180071efd  test    rdi, rdi
0x180071f00  jnz     short loc_180071F20
0x180071f02  imul    rax, r13, 18Ch
0x180071f09  mov     qword ptr [rax+rsi+178h], 0FFFFFFFFFFFFFFFFh
0x180071f15  mov     dword ptr [rax+rsi+174h], 0FFFFFFFFh
0x180071f20  imul    r12, r13, 18Ch
0x180071f27  lea     rcx, [rsi+10h]
0x180071f2b  mov     r8, rbx
0x180071f2e  add     rcx, r12
0x180071f31  lea     rdx, [rsp+78h+arg_0]
0x180071f39  call    BReadDataInGlobalNode
0x180071f3e  test    eax, eax
0x180071f40  jz      short loc_180071F98
0x180071f42  mov     ecx, [rsp+78h+arg_0]
0x180071f49  mov     rax, [rbx]
0x180071f4c  cmp     dword ptr [rcx+rax], 1
0x180071f50  jnz     short loc_180071F98
0x180071f52  test    rdi, rdi
0x180071f55  jz      short loc_180071F96
0x180071f57  mov     r9, rbx
0x180071f5a  mov     r8d, ebp
0x180071f5d  or      edx, 0FFFFFFFFh
0x180071f60  mov     ecx, r15d
0x180071f63  mov     rax, rdi
0x180071f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071f6b  test    eax, eax
0x180071f6d  jnz     short loc_180071F91
0x180071f6f  mov     r8d, r15d
0x180071f72  lea     rdx, aDwcountsynthfe_0; "DwCountSynthFeatures: Unable to create "...
0x180071f79  lea     rcx, aDwcountsynthfe; "DwCountSynthFeatures"
0x180071f80  call    WriteDbgTraceErrorGpd
0x180071f85  mov     dword ptr [r12+rsi+17Ch], 0FFFFFFFFh
0x180071f91  mov     r11, [rsp+78h+var_48]
0x180071f96  inc     ebp
0x180071f98  mov     eax, [r12+rsi+58h]
0x180071f9d  cmp     eax, 7FFFFFFFh
0x180071fa2  jz      loc_180072075
0x180071fa8  test    eax, eax
0x180071faa  jns     short loc_180071FC4
0x180071fac  lea     rdx, aInternalErrorD; "Internal error:  DwCountSynthFeatures -"...
0x180071fb3  lea     rcx, aDwcountsynthfe; "DwCountSynthFeatures"
0x180071fba  call    WriteDbgTraceErrorGpd
0x180071fbf  jmp     loc_180072075
0x180071fc4  mov     edx, [r12+rsi+188h]
0x180071fcc  xor     r14d, r14d
0x180071fcf  mov     [rsp+78h+arg_10], edx
0x180071fd6  test    edx, edx
0x180071fd8  jz      loc_180072075
0x180071fde  mov     eax, [r12+rsi+58h]
0x180071fe3  or      r8d, 0FFFFFFFFh
0x180071fe7  lea     rcx, [rax+rax*4]
0x180071feb  cmp     [r11+rcx*4+4], r14d
0x180071ff0  jz      short loc_180072003
0x180071ff2  mov     eax, [r11+rcx*4+8]
0x180071ff7  cmp     eax, r8d
0x180071ffa  jnz     short loc_180071FE7
0x180071ffc  cmp     [r11+rcx*4+4], r8d
0x180072001  jnz     short loc_180072069
0x180072003  cmp     dword ptr [r11+rcx*4+10h], 1
0x180072009  jnz     short loc_180072069
0x18007200b  mov     ecx, [r11+rcx*4+0Ch]
0x180072010  mov     rax, [rbx]
0x180072013  cmp     dword ptr [rcx+rax], 1
0x180072017  jnz     short loc_180072069
0x180072019  test    rdi, rdi
0x18007201c  jz      short loc_180072067
0x18007201e  mov     r9, rbx
0x180072021  mov     r8d, ebp
0x180072024  mov     edx, r14d
0x180072027  mov     ecx, r15d
0x18007202a  mov     rax, rdi
0x18007202d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072032  test    eax, eax
0x180072034  jnz     short loc_18007205B
0x180072036  mov     r9d, r14d
0x180072039  lea     rdx, aDwcountsynthfe_1; "DwCountSynthFeatures: Unable to create "...
0x180072040  mov     r8d, r15d
0x180072043  lea     rcx, aDwcountsynthfe; "DwCountSynthFeatures"
0x18007204a  call    WriteDbgTraceErrorGpd
0x18007204f  mov     dword ptr [r12+rsi+170h], 7FFFFFFFh
0x18007205b  mov     r11, [rsp+78h+var_48]
0x180072060  mov     edx, [rsp+78h+arg_10]
0x180072067  inc     ebp
0x180072069  inc     r14d
0x18007206c  cmp     r14d, edx
0x18007206f  jb      loc_180071FDE
0x180072075  mov     r11, [rsp+78h+var_48]
0x18007207a  inc     r15d
0x18007207d  inc     r13
0x180072080  cmp     r15d, [rsp+78h+arg_18]
0x180072088  jb      loc_180071EFD
0x18007208e  test    rdi, rdi
0x180072091  jz      short loc_18007209B
0x180072093  mov     rcx, rbx
0x180072096  call    BEnableInvInstallableCombos
0x18007209b  mov     eax, ebp
0x18007209d  mov     rbx, [rsp+78h+arg_8]
0x1800720a5  add     rsp, 40h
0x1800720a9  pop     r15
0x1800720ab  pop     r14
0x1800720ad  pop     r13
0x1800720af  pop     r12
0x1800720b1  pop     rdi
0x1800720b2  pop     rsi
0x1800720b3  pop     rbp
0x1800720b4  retn
```
