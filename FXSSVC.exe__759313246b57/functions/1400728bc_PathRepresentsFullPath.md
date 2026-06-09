# PathRepresentsFullPath

- ea: `0x1400728bc`
- end: `0x140072a6a`
- name: `PathRepresentsFullPath`
- size: `430`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c004`
- `0x14001ee40`
- `0x1400530d0`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x1400698ec`
- `0x14006998c`
- `0x1400728bc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140072979`
- `KERNEL32!GetLastError` at `0x140072a1c`
- `KERNEL32!GetLastError` at `0x140072979`
- `KERNEL32!GetLastError` at `0x140072a1c`
- `KERNEL32!GetFullPathNameW` at `0x140072943`
- `KERNEL32!GetFullPathNameW` at `0x1400729f4`
- `KERNEL32!GetFullPathNameW` at `0x140072943`
- `KERNEL32!GetFullPathNameW` at `0x1400729f4`
- `msvcrt!_wcsicmp` at `0x140072a3c`
- `msvcrt!_wcsicmp` at `0x140072a3c`

## pseudocode

```c
_BOOL8 __fastcall PathRepresentsFullPath(wchar_t *String1)
{
  CMapDeviceId *v2; // rcx
  BOOL v4; // esi
  DWORD FullPathNameW; // eax
  wchar_t *v6; // rbx
  DWORD LastError; // eax
  __int64 v8; // rdx
  DWORD v9; // ebp
  WCHAR *v10; // rax
  DWORD v11; // eax

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( String1 )
  {
    v4 = 0;
    FullPathNameW = GetFullPathNameW(String1, 0, 0, 0);
    if ( FullPathNameW )
    {
      v9 = FullPathNameW + 1;
      v10 = (WCHAR *)pMemAlloc(2LL * (FullPathNameW + 1));
      v6 = v10;
      if ( !v10 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
        }
        goto LABEL_29;
      }
      v11 = GetFullPathNameW(String1, v9, v10, 0);
      if ( v11 )
      {
        if ( v11 <= v9 )
          v4 = _wcsicmp(String1, v6) == 0;
        goto LABEL_29;
      }
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_29:
        pMemFree(v6);
        return v4;
      }
      LastError = GetLastError();
      v8 = 105;
    }
    else
    {
      v6 = 0;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      LastError = GetLastError();
      v8 = 103;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids, LastError);
    goto LABEL_29;
  }
  if ( v2 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 2u )
    WPP_SF_(*((_QWORD *)v2 + 2), 102, &WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1400728bc  push    rbx
0x1400728be  push    rbp
0x1400728bf  push    rsi
0x1400728c0  push    rdi
0x1400728c1  push    r12
0x1400728c3  push    r15
0x1400728c5  sub     rsp, 28h
0x1400728c9  mov     rdi, rcx
0x1400728cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400728d3  lea     r15, WPP_GLOBAL_Control
0x1400728da  lea     r12, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x1400728e1  cmp     rcx, r15
0x1400728e4  jz      short loc_14007290A
0x1400728e6  test    byte ptr [rcx+1Ch], 2
0x1400728ea  jz      short loc_14007290A
0x1400728ec  cmp     byte ptr [rcx+19h], 5
0x1400728f0  jb      short loc_14007290A
0x1400728f2  mov     rcx, [rcx+10h]
0x1400728f6  mov     edx, 65h ; 'e'
0x1400728fb  mov     r8, r12
0x1400728fe  call    WPP_SF_
0x140072903  mov     rcx, cs:WPP_GLOBAL_Control
0x14007290a  test    rdi, rdi
0x14007290d  jnz     short loc_140072936
0x14007290f  cmp     rcx, r15
0x140072912  jz      short loc_14007292F
0x140072914  test    byte ptr [rcx+1Ch], 2
0x140072918  jz      short loc_14007292F
0x14007291a  cmp     byte ptr [rcx+19h], 2
0x14007291e  jb      short loc_14007292F
0x140072920  mov     rcx, [rcx+10h]
0x140072924  lea     edx, [rdi+66h]
0x140072927  mov     r8, r12
0x14007292a  call    WPP_SF_
0x14007292f  xor     eax, eax
0x140072931  jmp     loc_140072A5C
0x140072936  xor     r9d, r9d; lpFilePart
0x140072939  xor     r8d, r8d; lpBuffer
0x14007293c  xor     edx, edx; nBufferLength
0x14007293e  mov     rcx, rdi; lpFileName
0x140072941  xor     esi, esi
0x140072943  call    cs:__imp_GetFullPathNameW
0x14007294a  nop     dword ptr [rax+rax+00h]
0x14007294f  test    eax, eax
0x140072951  jnz     short loc_1400729A3
0x140072953  xor     ebx, ebx
0x140072955  mov     rax, cs:WPP_GLOBAL_Control
0x14007295c  cmp     rax, r15
0x14007295f  jz      loc_140072A52
0x140072965  test    byte ptr [rax+1Ch], 2
0x140072969  jz      loc_140072A52
0x14007296f  cmp     byte ptr [rax+19h], 2
0x140072973  jb      loc_140072A52
0x140072979  call    cs:__imp_GetLastError
0x140072980  nop     dword ptr [rax+rax+00h]
0x140072985  lea     edx, [rsi+67h]
0x140072988  mov     rcx, cs:WPP_GLOBAL_Control
0x14007298f  mov     r9d, eax
0x140072992  mov     r8, r12
0x140072995  mov     rcx, [rcx+10h]
0x140072999  call    WPP_SF_d
0x14007299e  jmp     loc_140072A52
0x1400729a3  lea     ebp, [rax+1]
0x1400729a6  mov     ecx, ebp
0x1400729a8  add     rcx, rcx; dwBytes
0x1400729ab  call    pMemAlloc
0x1400729b0  mov     rbx, rax
0x1400729b3  test    rax, rax
0x1400729b6  jnz     short loc_1400729E9
0x1400729b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400729bf  cmp     rcx, r15
0x1400729c2  jz      loc_140072A52
0x1400729c8  test    byte ptr [rcx+1Ch], 2
0x1400729cc  jz      loc_140072A52
0x1400729d2  cmp     byte ptr [rcx+19h], 2
0x1400729d6  jb      short loc_140072A52
0x1400729d8  mov     rcx, [rcx+10h]
0x1400729dc  lea     edx, [rax+68h]
0x1400729df  mov     r8, r12
0x1400729e2  call    WPP_SF_
0x1400729e7  jmp     short loc_140072A52
0x1400729e9  xor     r9d, r9d; lpFilePart
0x1400729ec  mov     r8, rbx; lpBuffer
0x1400729ef  mov     edx, ebp; nBufferLength
0x1400729f1  mov     rcx, rdi; lpFileName
0x1400729f4  call    cs:__imp_GetFullPathNameW
0x1400729fb  nop     dword ptr [rax+rax+00h]
0x140072a00  test    eax, eax
0x140072a02  jnz     short loc_140072A32
0x140072a04  mov     rax, cs:WPP_GLOBAL_Control
0x140072a0b  cmp     rax, r15
0x140072a0e  jz      short loc_140072A52
0x140072a10  test    byte ptr [rax+1Ch], 2
0x140072a14  jz      short loc_140072A52
0x140072a16  cmp     byte ptr [rax+19h], 2
0x140072a1a  jb      short loc_140072A52
0x140072a1c  call    cs:__imp_GetLastError
0x140072a23  nop     dword ptr [rax+rax+00h]
0x140072a28  mov     edx, 69h ; 'i'
0x140072a2d  jmp     loc_140072988
0x140072a32  cmp     eax, ebp
0x140072a34  ja      short loc_140072A52
0x140072a36  mov     rdx, rbx; String2
0x140072a39  mov     rcx, rdi; String1
0x140072a3c  call    cs:__imp__wcsicmp
0x140072a43  nop     dword ptr [rax+rax+00h]
0x140072a48  test    eax, eax
0x140072a4a  mov     ecx, 1
0x140072a4f  cmovz   esi, ecx
0x140072a52  mov     rcx, rbx; lpMem
0x140072a55  call    pMemFree
0x140072a5a  mov     eax, esi
0x140072a5c  add     rsp, 28h
0x140072a60  pop     r15
0x140072a62  pop     r12
0x140072a64  pop     rdi
0x140072a65  pop     rsi
0x140072a66  pop     rbp
0x140072a67  pop     rbx
0x140072a68  retn
```
