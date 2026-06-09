# GetVolumeMountPoint(ushort const *,ushort *,ulong)

- ea: `0x180060870`
- end: `0x180060bad`
- name: `?GetVolumeMountPoint@@YAJPEBGPEAGK@Z`
- size: `829`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x180064b38`

## callees

- `0x180009f60`
- `0x18000dd60`
- `0x18000f760`
- `0x180024a18`
- `0x18002e628`
- `0x180034070`
- `0x180034d28`
- `0x180060870`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060b79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180060b79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060933`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180060933`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006091c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060b65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006091c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180060b65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800608fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800608fb`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800608e7`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x1800608e7`

## pseudocode

```c
__int64 __fastcall GetVolumeMountPoint(LPCWSTR lpszVolumeName, unsigned __int16 *a2)
{
  ULONG v3; // r12d
  WCHAR *v4; // rsi
  DWORD v5; // ebx
  unsigned int i; // edi
  SIZE_T v7; // rbx
  HANDLE v8; // rax
  int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int KnownLastErrorHR; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned __int64 v17; // r15
  unsigned __int64 v18; // r13
  unsigned __int64 j; // r14
  unsigned int v20; // eax
  __int64 v21; // r10
  ULONGLONG v22; // rbp
  unsigned int v23; // eax
  __int64 v24; // r10
  unsigned __int64 v25; // r8
  HANDLE ProcessHeap; // rax
  ULONG pulResult; // [rsp+20h] [rbp-68h] BYREF
  ULONGLONG ullOperand; // [rsp+28h] [rbp-60h] BYREF
  unsigned __int16 *v30; // [rsp+30h] [rbp-58h]
  DWORD cchReturnLength; // [rsp+38h] [rbp-50h] BYREF

  v30 = a2;
  ullOperand = 0;
  v3 = 260;
  cchReturnLength = 0;
  pulResult = 260;
  v4 = 0;
  v5 = 0;
  memset_0(a2, 0, 0x208u);
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      if ( i == 3 )
      {
        v16 = 2147549183LL;
        v9 = -2147418113;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_48;
        v15 = 52;
LABEL_47:
        WPP_SF_d(v14[2], v15, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v16);
        goto LABEL_48;
      }
LABEL_24:
      v17 = 0;
      v18 = v5;
      for ( j = 0; j < v18; j += v22 )
      {
        v20 = StringCchLengthW(&v4[j], v18 - j, &ullOperand);
        v9 = v20;
        if ( v20 )
        {
          if ( (PVOID *)v21 != &WPP_GLOBAL_Control && (*(_BYTE *)(v21 + 28) & 0x40) != 0 )
            WPP_SF_d(*(_QWORD *)(v21 + 16), 53, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v20);
          if ( v9 < 0 )
            goto LABEL_48;
        }
        v22 = ullOperand;
        if ( !ullOperand )
          break;
        if ( ullOperand < v3 )
        {
          v23 = ULongLongToULong(ullOperand, &pulResult);
          v9 = v23;
          if ( v23 )
          {
            if ( (PVOID *)v24 != &WPP_GLOBAL_Control && (*(_BYTE *)(v24 + 28) & 0x40) != 0 )
              WPP_SF_d(*(_QWORD *)(v24 + 16), 54, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v23);
            if ( v9 < 0 )
              goto LABEL_48;
          }
          v3 = pulResult;
          v17 = j;
        }
      }
      v25 = v17 + v3;
      if ( v4[v25 - 1] == 92 )
        v4[v25 - 1] = 0;
      KnownLastErrorHR = StringCchCopyW(v30, 0x104u, &v4[v17]);
      v9 = KnownLastErrorHR;
      if ( !KnownLastErrorHR )
        goto LABEL_48;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_48;
      v15 = 55;
LABEL_46:
      v16 = KnownLastErrorHR;
      goto LABEL_47;
    }
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v4, v5, &cchReturnLength) )
      break;
    if ( GetLastError() != 234 )
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v9 = KnownLastErrorHR;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v15 = 50;
        goto LABEL_46;
      }
LABEL_48:
      if ( v4 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
      }
      return (unsigned int)v9;
    }
    if ( cchReturnLength <= 1 )
    {
      v9 = 0;
      goto LABEL_48;
    }
    v7 = 2LL * cchReturnLength;
    v8 = GetProcessHeap();
    v4 = (WCHAR *)HeapAlloc(v8, 8u, v7);
    if ( !v4 )
    {
      v9 = -2147024882;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v11 = 51;
        v12 = 2147942414LL;
LABEL_19:
        WPP_SF_d(v10[2], v11, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids, v12);
        return (unsigned int)v9;
      }
      return (unsigned int)v9;
    }
    v5 = cchReturnLength;
  }
  if ( v4 )
    goto LABEL_24;
  v12 = 2147549183LL;
  v9 = -2147418113;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v11 = 49;
    goto LABEL_19;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180060870  mov     [rsp+arg_10], rbx
0x180060875  push    rbp
0x180060876  push    rsi
0x180060877  push    rdi
0x180060878  push    r12
0x18006087a  push    r13
0x18006087c  push    r14
0x18006087e  push    r15
0x180060880  sub     rsp, 50h
0x180060884  mov     rax, cs:__security_cookie
0x18006088b  xor     rax, rsp
0x18006088e  mov     [rsp+88h+var_48], rax
0x180060893  mov     rax, rdx
0x180060896  mov     [rsp+88h+var_58], rdx
0x18006089b  mov     rbp, rcx
0x18006089e  mov     [rsp+88h+ullOperand], 0
0x1800608a7  mov     r12d, 104h
0x1800608ad  mov     [rsp+88h+cchReturnLength], 0
0x1800608b5  mov     rcx, rax; void *
0x1800608b8  mov     [rsp+88h+pulResult], r12d
0x1800608bd  xor     edx, edx; Val
0x1800608bf  mov     r8d, 208h; Size
0x1800608c5  xor     esi, esi
0x1800608c7  xor     ebx, ebx
0x1800608c9  call    memset_0
0x1800608ce  xor     edi, edi
0x1800608d0  cmp     edi, 3
0x1800608d3  jnb     loc_1800609FF
0x1800608d9  lea     r9, [rsp+88h+cchReturnLength]; lpcchReturnLength
0x1800608de  mov     r8d, ebx; cchBufferLength
0x1800608e1  mov     rdx, rsi; lpszVolumePathNames
0x1800608e4  mov     rcx, rbp; lpszVolumeName
0x1800608e7  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x1800608ee  nop     dword ptr [rax+rax+00h]
0x1800608f3  test    eax, eax
0x1800608f5  jnz     loc_1800609B8
0x1800608fb  call    cs:__imp_GetLastError
0x180060902  nop     dword ptr [rax+rax+00h]
0x180060907  cmp     eax, 0EAh
0x18006090c  jnz     short loc_180060986
0x18006090e  cmp     [rsp+88h+cchReturnLength], 1
0x180060913  jbe     short loc_18006097F
0x180060915  mov     ebx, [rsp+88h+cchReturnLength]
0x180060919  add     rbx, rbx
0x18006091c  call    cs:__imp_GetProcessHeap
0x180060923  nop     dword ptr [rax+rax+00h]
0x180060928  mov     r8, rbx; dwBytes
0x18006092b  mov     edx, 8; dwFlags
0x180060930  mov     rcx, rax; hHeap
0x180060933  call    cs:__imp_HeapAlloc
0x18006093a  nop     dword ptr [rax+rax+00h]
0x18006093f  mov     rsi, rax
0x180060942  test    rax, rax
0x180060945  jz      short loc_18006094F
0x180060947  mov     ebx, [rsp+88h+cchReturnLength]
0x18006094b  inc     edi
0x18006094d  jmp     short loc_1800608D0
0x18006094f  mov     ebx, 8007000Eh
0x180060954  mov     rcx, cs:WPP_GLOBAL_Control
0x18006095b  lea     rdi, WPP_GLOBAL_Control
0x180060962  cmp     rcx, rdi
0x180060965  jz      loc_180060B85
0x18006096b  test    byte ptr [rcx+1Ch], 40h
0x18006096f  jz      loc_180060B85
0x180060975  mov     edx, 33h ; '3'
0x18006097a  mov     r9d, ebx
0x18006097d  jmp     short loc_1800609EA
0x18006097f  xor     ebx, ebx
0x180060981  jmp     loc_180060B60
0x180060986  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18006098b  mov     ebx, eax
0x18006098d  mov     rcx, cs:WPP_GLOBAL_Control
0x180060994  lea     rdi, WPP_GLOBAL_Control
0x18006099b  cmp     rcx, rdi
0x18006099e  jz      loc_180060B60
0x1800609a4  test    byte ptr [rcx+1Ch], 40h
0x1800609a8  jz      loc_180060B60
0x1800609ae  mov     edx, 32h ; '2'
0x1800609b3  jmp     loc_180060B4D
0x1800609b8  test    rsi, rsi
0x1800609bb  jnz     short loc_180060A35
0x1800609bd  mov     r9d, 8000FFFFh
0x1800609c3  mov     ebx, r9d
0x1800609c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800609cd  lea     rdi, WPP_GLOBAL_Control
0x1800609d4  cmp     rcx, rdi
0x1800609d7  jz      loc_180060B85
0x1800609dd  test    byte ptr [rcx+1Ch], 40h
0x1800609e1  jz      loc_180060B85
0x1800609e7  lea     edx, [rsi+31h]
0x1800609ea  mov     rcx, [rcx+10h]
0x1800609ee  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x1800609f5  call    WPP_SF_d
0x1800609fa  jmp     loc_180060B85
0x1800609ff  jnz     short loc_180060A35
0x180060a01  mov     r9d, 8000FFFFh
0x180060a07  mov     ebx, r9d
0x180060a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180060a11  lea     rdi, WPP_GLOBAL_Control
0x180060a18  cmp     rcx, rdi
0x180060a1b  jz      loc_180060B60
0x180060a21  test    byte ptr [rcx+1Ch], 40h
0x180060a25  jz      loc_180060B60
0x180060a2b  mov     edx, 34h ; '4'
0x180060a30  jmp     loc_180060B50
0x180060a35  mov     r10, cs:WPP_GLOBAL_Control
0x180060a3c  lea     rdi, WPP_GLOBAL_Control
0x180060a43  xor     r15d, r15d
0x180060a46  mov     r13d, ebx
0x180060a49  xor     r14d, r14d
0x180060a4c  cmp     r14, r13
0x180060a4f  jnb     loc_180060B06
0x180060a55  mov     rdx, r13
0x180060a58  lea     rcx, [rsi+r14*2]; unsigned __int16 *
0x180060a5c  sub     rdx, r14; unsigned __int64
0x180060a5f  lea     r8, [rsp+88h+ullOperand]; unsigned __int64 *
0x180060a64  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180060a69  mov     ebx, eax
0x180060a6b  test    eax, eax
0x180060a6d  jz      short loc_180060AA2
0x180060a6f  cmp     r10, rdi
0x180060a72  jz      short loc_180060A9A
0x180060a74  test    byte ptr [r10+1Ch], 40h
0x180060a79  jz      short loc_180060A9A
0x180060a7b  mov     rcx, [r10+10h]
0x180060a7f  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x180060a86  mov     edx, 35h ; '5'
0x180060a8b  mov     r9d, eax
0x180060a8e  call    WPP_SF_d
0x180060a93  mov     r10, cs:WPP_GLOBAL_Control
0x180060a9a  test    ebx, ebx
0x180060a9c  js      loc_180060B60
0x180060aa2  mov     rbp, [rsp+88h+ullOperand]
0x180060aa7  test    rbp, rbp
0x180060aaa  jz      short loc_180060B06
0x180060aac  mov     eax, r12d
0x180060aaf  cmp     rbp, rax
0x180060ab2  jnb     short loc_180060AFE
0x180060ab4  lea     rdx, [rsp+88h+pulResult]; pulResult
0x180060ab9  mov     rcx, rbp; ullOperand
0x180060abc  call    ULongLongToULong
0x180060ac1  mov     ebx, eax
0x180060ac3  test    eax, eax
0x180060ac5  jz      short loc_180060AF6
0x180060ac7  cmp     r10, rdi
0x180060aca  jz      short loc_180060AF2
0x180060acc  test    byte ptr [r10+1Ch], 40h
0x180060ad1  jz      short loc_180060AF2
0x180060ad3  mov     rcx, [r10+10h]
0x180060ad7  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x180060ade  mov     edx, 36h ; '6'
0x180060ae3  mov     r9d, eax
0x180060ae6  call    WPP_SF_d
0x180060aeb  mov     r10, cs:WPP_GLOBAL_Control
0x180060af2  test    ebx, ebx
0x180060af4  js      short loc_180060B60
0x180060af6  mov     r12d, [rsp+88h+pulResult]
0x180060afb  mov     r15, r14
0x180060afe  add     r14, rbp
0x180060b01  jmp     loc_180060A4C
0x180060b06  mov     r8d, r12d
0x180060b09  add     r8, r15
0x180060b0c  cmp     word ptr [rsi+r8*2-2], 5Ch ; '\'
0x180060b13  jnz     short loc_180060B1D
0x180060b15  xor     eax, eax
0x180060b17  mov     [rsi+r8*2-2], ax
0x180060b1d  mov     rcx, [rsp+88h+var_58]; unsigned __int16 *
0x180060b22  lea     r8, [rsi+r15*2]; unsigned __int16 *
0x180060b26  mov     edx, 104h; unsigned __int64
0x180060b2b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180060b30  mov     ebx, eax
0x180060b32  test    eax, eax
0x180060b34  jz      short loc_180060B60
0x180060b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180060b3d  cmp     rcx, rdi
0x180060b40  jz      short loc_180060B60
0x180060b42  test    byte ptr [rcx+1Ch], 40h
0x180060b46  jz      short loc_180060B60
0x180060b48  mov     edx, 37h ; '7'
0x180060b4d  mov     r9d, eax
0x180060b50  mov     rcx, [rcx+10h]
0x180060b54  lea     r8, WPP_2ae62ccbb2c831f569890b5ead6e2a46_Traceguids
0x180060b5b  call    WPP_SF_d
0x180060b60  test    rsi, rsi
0x180060b63  jz      short loc_180060B85
0x180060b65  call    cs:__imp_GetProcessHeap
0x180060b6c  nop     dword ptr [rax+rax+00h]
0x180060b71  mov     r8, rsi; lpMem
0x180060b74  xor     edx, edx; dwFlags
0x180060b76  mov     rcx, rax; hHeap
0x180060b79  call    cs:__imp_HeapFree
0x180060b80  nop     dword ptr [rax+rax+00h]
0x180060b85  mov     eax, ebx
0x180060b87  mov     rcx, [rsp+88h+var_48]
0x180060b8c  xor     rcx, rsp; StackCookie
0x180060b8f  call    __security_check_cookie
0x180060b94  mov     rbx, [rsp+88h+arg_10]
0x180060b9c  add     rsp, 50h
0x180060ba0  pop     r15
0x180060ba2  pop     r14
0x180060ba4  pop     r13
0x180060ba6  pop     r12
0x180060ba8  pop     rdi
0x180060ba9  pop     rsi
0x180060baa  pop     rbp
0x180060bab  retn
```
