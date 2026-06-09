# HtCreateHandleTable

- ea: `0x180003f50`
- end: `0x18000414b`
- name: `HtCreateHandleTable`
- size: `507`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003f50`
- `0x180004260`
- `0x180004b80`
- `0x180004cb0`
- `0x18000b774`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000409d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000409d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000408f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000408f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004011`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180004011`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003fcc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003fcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003fac`

## string_xrefs

- `0x18000406e`: `HtCreateHandleTable`
- `0x1800040e0`: `HtCreateHandleTable`
- `0x180004120`: `HtCreateHandleTable`

## pseudocode

```c
__int64 __fastcall HtCreateHandleTable(__int64 a1, unsigned int a2, _QWORD *a3)
{
  unsigned __int64 v5; // rdi
  unsigned int v6; // edi
  unsigned int v7; // ebp
  HANDLE ProcessHeap; // rbx
  _DWORD *v9; // rax
  int v10; // r8d
  _DWORD *v11; // rbx
  char v13; // r8
  DWORD LastError; // eax
  int v15; // r8d
  LPVOID v16; // [rsp+80h] [rbp+18h] BYREF

  if ( a3 )
  {
    *a3 = 0;
    v5 = (unsigned __int64)~a1 >> 4;
    if ( v5 > 0xFFFFFFF )
      LODWORD(v5) = 0xFFFFFFF;
    v6 = v5 & 0xFFFFFFE0;
    if ( a2 <= v6 )
    {
      v7 = 14;
      if ( a2 )
        v6 = (a2 + 31) & 0xFFFFFFE0;
      ProcessHeap = GetProcessHeap();
      if ( !ProcessHeap )
      {
        LastError = GetLastError();
        if ( LastError )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_sdd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              v15,
              (unsigned int)"HtCreateHandleTable",
              233,
              LastError);
          return v7;
        }
      }
      v9 = HeapAlloc(ProcessHeap, 8u, 0x78u);
      v11 = v9;
      if ( !v9 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v10, (unsigned int)"HtCreateHandleTable", 233, 120);
        return v7;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sdqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          v10,
          (unsigned int)"HtCreateHandleTable",
          233,
          (char)v9,
          120);
      v16 = v11;
      if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v11 + 2), 0x80001000) )
      {
        *v11 = 1950888524;
        *((_QWORD *)v11 + 6) = a1;
        v11[19] = 32;
        v11[14] = v6;
        v11[28] = 0xFFFFFFF;
        v11[25] = 0xFFFFFFF;
        v11[22] = 0xFFFFFFF;
        if ( (unsigned int)HtGrowTable(v11) )
        {
          v7 = 0;
          *a3 = v11;
          return v7;
        }
        DeleteCriticalSection((LPCRITICAL_SECTION)(v11 + 2));
        v13 = -4;
      }
      else
      {
        v13 = 1;
      }
      FreeMemory(&v16, (int)"HtCreateHandleTable", v13);
      return v7;
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180003f50  push    rsi
0x180003f52  push    rdi
0x180003f53  push    r12
0x180003f55  push    r15
0x180003f57  sub     rsp, 48h
0x180003f5b  mov     rsi, r8
0x180003f5e  mov     r15, rcx
0x180003f61  test    r8, r8
0x180003f64  jz      loc_180004084
0x180003f6a  mov     r12d, 0FFFFFFFh
0x180003f70  mov     qword ptr [r8], 0
0x180003f77  mov     rdi, rcx
0x180003f7a  not     rdi
0x180003f7d  shr     rdi, 4
0x180003f81  cmp     rdi, r12
0x180003f84  cmova   rdi, r12
0x180003f88  and     edi, 0FFFFFFE0h
0x180003f8b  cmp     edx, edi
0x180003f8d  ja      loc_180004084
0x180003f93  mov     [rsp+68h+arg_0], rbx
0x180003f98  mov     [rsp+68h+arg_8], rbp
0x180003f9d  mov     ebp, 0Eh
0x180003fa2  test    edx, edx
0x180003fa4  jz      short loc_180003FAC
0x180003fa6  lea     edi, [rdx+1Fh]
0x180003fa9  and     edi, 0FFFFFFE0h
0x180003fac  call    cs:__imp_GetProcessHeap
0x180003fb2  mov     rbx, rax
0x180003fb5  test    rax, rax
0x180003fb8  jz      loc_18000409D
0x180003fbe  mov     edx, 8; dwFlags
0x180003fc3  mov     r8d, 78h ; 'x'; dwBytes
0x180003fc9  mov     rcx, rbx; hHeap
0x180003fcc  call    cs:__imp_HeapAlloc
0x180003fd2  mov     rbx, rax
0x180003fd5  test    rax, rax
0x180003fd8  jz      loc_1800040F9
0x180003fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fe5  lea     rdx, WPP_GLOBAL_Control
0x180003fec  mov     [rsp+68h+var_28], r14
0x180003ff1  cmp     rcx, rdx
0x180003ff4  jz      short loc_180004000
0x180003ff6  test    byte ptr [rcx+1Ch], 2
0x180003ffa  jnz     loc_18000411C
0x180004000  mov     edx, 80001000h; dwSpinCount
0x180004005  mov     [rsp+68h+arg_10], rbx
0x18000400d  lea     rcx, [rbx+8]; lpCriticalSection
0x180004011  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180004017  test    eax, eax
0x180004019  jz      short loc_180004068
0x18000401b  mov     dword ptr [rbx], 7448324Ch
0x180004021  mov     rcx, rbx
0x180004024  mov     [rbx+30h], r15
0x180004028  mov     dword ptr [rbx+4Ch], 20h ; ' '
0x18000402f  mov     [rbx+38h], edi
0x180004032  mov     [rbx+70h], r12d
0x180004036  mov     [rbx+64h], r12d
0x18000403a  mov     [rbx+58h], r12d
0x18000403e  call    HtGrowTable
0x180004043  test    eax, eax
0x180004045  jz      short loc_18000408B
0x180004047  xor     ebp, ebp
0x180004049  mov     [rsi], rbx
0x18000404c  mov     r14, [rsp+68h+var_28]
0x180004051  mov     rbx, [rsp+68h+arg_0]
0x180004056  mov     eax, ebp
0x180004058  mov     rbp, [rsp+68h+arg_8]
0x18000405d  add     rsp, 48h
0x180004061  pop     r15
0x180004063  pop     r12
0x180004065  pop     rdi
0x180004066  pop     rsi
0x180004067  retn
0x180004068  mov     r8d, 101h
0x18000406e  lea     rdx, aHtcreatehandle_0; "HtCreateHandleTable"
0x180004075  lea     rcx, [rsp+68h+arg_10]
0x18000407d  call    FreeMemory
0x180004082  jmp     short loc_18000404C
0x180004084  mov     eax, 57h ; 'W'
0x180004089  jmp     short loc_18000405D
0x18000408b  lea     rcx, [rbx+8]; lpCriticalSection
0x18000408f  call    cs:__imp_DeleteCriticalSection
0x180004095  mov     r8d, 0FCh
0x18000409b  jmp     short loc_18000406E
0x18000409d  call    cs:__imp_GetLastError
0x1800040a3  test    eax, eax
0x1800040a5  jz      loc_180003FBE
0x1800040ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800040b2  lea     rdx, WPP_GLOBAL_Control
0x1800040b9  cmp     rcx, rdx
0x1800040bc  jz      short loc_180004051
0x1800040be  test    byte ptr [rcx+1Ch], 4
0x1800040c2  jz      short loc_180004051
0x1800040c4  mov     edx, 0Ah
0x1800040c9  mov     dword ptr [rsp+68h+var_40], eax
0x1800040cd  jmp     short loc_1800040DC
0x1800040cf  mov     edx, 0Bh
0x1800040d4  mov     dword ptr [rsp+68h+var_40], 78h ; 'x'
0x1800040dc  mov     rcx, [rcx+10h]
0x1800040e0  lea     r9, aHtcreatehandle_0; "HtCreateHandleTable"
0x1800040e7  mov     [rsp+68h+var_48], 0E9h
0x1800040ef  call    WPP_SF_sdd
0x1800040f4  jmp     loc_180004051
0x1800040f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180004100  lea     rdx, WPP_GLOBAL_Control
0x180004107  cmp     rcx, rdx
0x18000410a  jz      loc_180004051
0x180004110  test    byte ptr [rcx+1Ch], 4
0x180004114  jz      loc_180004051
0x18000411a  jmp     short loc_1800040CF
0x18000411c  mov     rcx, [rcx+10h]
0x180004120  lea     r9, aHtcreatehandle_0; "HtCreateHandleTable"
0x180004127  mov     [rsp+68h+var_38], 78h ; 'x'
0x18000412f  mov     edx, 0Ch
0x180004134  mov     [rsp+68h+var_40], rbx
0x180004139  mov     [rsp+68h+var_48], 0E9h
0x180004141  call    WPP_SF_sdqd
0x180004146  jmp     loc_180004000
```
