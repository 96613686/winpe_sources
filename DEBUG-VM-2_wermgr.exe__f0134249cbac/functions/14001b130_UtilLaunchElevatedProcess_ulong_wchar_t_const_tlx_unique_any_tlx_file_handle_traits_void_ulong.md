# UtilLaunchElevatedProcess(ulong,wchar_t const *,tlx::unique_any<tlx::file_handle_traits> *,void * *,ulong)

- ea: `0x14001b130`
- end: `0x14001b4a2`
- name: `?UtilLaunchElevatedProcess@@YAJKPEB_WPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAPEAXK@Z`
- size: `882`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x14000659c`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x14000e318`
- `0x14000e340`
- `0x14001b130`
- `0x14001b4a8`
- `0x14001c930`
- `0x14001c9a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b41c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b405`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b41c`
- `ntdll!RtlNtStatusToDosError` at `0x14001b2ed`
- `ntdll!RtlNtStatusToDosError` at `0x14001b2ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b3fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b47b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b3fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001b47b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14001b1e7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14001b1e7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001b46b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001b46b`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14001b1b8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14001b1b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 UtilLaunchElevatedProcess()
{
  wchar_t *v0; // rdi
  HANDLE FileMappingW; // rax
  void *v2; // rsi
  unsigned __int64 v3; // r14
  __int64 v4; // rax
  const wchar_t *v5; // rcx
  __int64 v6; // rdx
  wchar_t *v7; // r8
  wchar_t v8; // r9
  unsigned int v9; // ebx
  wchar_t *v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  const wchar_t *v13; // rcx
  NTSTATUS v14; // eax
  signed int v15; // eax
  HANDLE v16; // rbx
  signed int v17; // eax
  signed int LastError; // eax
  _BYTE Src[1408]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v21; // [rsp+5C0h] [rbp+4C0h] BYREF
  char v22[38]; // [rsp+5C2h] [rbp+4C2h] BYREF
  int v23; // [rsp+5E8h] [rbp+4E8h]
  int v24; // [rsp+5ECh] [rbp+4ECh]
  HANDLE hObject; // [rsp+688h] [rbp+588h]
  _DWORD v26[14]; // [rsp+B40h] [rbp+A40h] BYREF
  __int64 v27; // [rsp+B78h] [rbp+A78h]
  int v28; // [rsp+C00h] [rbp+B00h]

  LOWORD(v26[0]) = 0;
  memset_0((char *)v26 + 2, 0, 0x576u);
  v21 = 0;
  memset_0(v22, 0, 0x576u);
  v0 = 0;
  FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x208u, 0);
  v2 = FileMappingW;
  v3 = (unsigned __int64)FileMappingW + 1;
  if ( (unsigned __int64)FileMappingW + 1 <= 1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 32;
      goto LABEL_40;
    }
  }
  else
  {
    v0 = (wchar_t *)MapViewOfFile(FileMappingW, 0x120116u, 0, 0, 0x208u);
    if ( v0 )
    {
      v4 = 2147483646;
      v5 = L"-k -lcq";
      v6 = 260;
      v7 = v0;
      do
      {
        if ( !v4 )
          break;
        v8 = *v5;
        if ( !*v5 )
          break;
        ++v5;
        *v7++ = v8;
        --v4;
        --v6;
      }
      while ( v6 );
      v9 = v6 == 0 ? 0x8007007A : 0;
      v10 = v7 - 1;
      if ( v6 )
        v10 = v7;
      *v10 = 0;
      if ( v6 )
      {
        memset_0(Src, 0, 0x578u);
        memcpy_0(v26, Src, 0x578u);
        v26[0] = 91751760;
        v26[10] = 1342177280;
        v26[12] = 1;
        v27 = (unsigned int)v2;
        v28 = 0;
        v14 = WersvcSendMessage(v13, (struct _WERSVC_MSG *)v26, (struct _WERSVC_MSG *)&v21);
        v15 = RtlNtStatusToDosError(v14);
        v9 = v15;
        if ( v15 > 0 )
          v9 = (unsigned __int16)v15 | 0x80070000;
        if ( (v9 & 0x80000000) == 0 )
        {
          if ( v23 == 1342177281 )
          {
            v16 = hObject;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
            if ( (unsigned __int64)v16 + 1 > 1 )
              CloseHandle(v16);
            v9 = 0;
          }
          else if ( v23 == 1342177282 )
          {
            v9 = v24 | 0x10000000;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v12 = 37;
              goto LABEL_40;
            }
          }
          else
          {
            v9 = -2147467259;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
          }
        }
        else
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v12 = 35;
            goto LABEL_40;
          }
        }
      }
      else
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 33;
LABEL_40:
          WPP_SF_d(v11[2], v12, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v9);
        }
      }
    }
    else
    {
      v17 = GetLastError();
      v9 = v17;
      if ( v17 > 0 )
        v9 = (unsigned __int16)v17 | 0x80070000;
    }
  }
  if ( v0 )
    UnmapViewOfFile(v0);
  if ( v3 > 1 )
    CloseHandle(v2);
  return v9;
}

```

## disassembly

```asm
0x14001b130  push    rbp
0x14001b132  push    rbx
0x14001b133  push    rsi
0x14001b134  push    rdi
0x14001b135  push    r14
0x14001b137  push    r15
0x14001b139  lea     rbp, [rsp-0FD8h]
0x14001b141  mov     eax, 10D8h
0x14001b146  call    _alloca_probe
0x14001b14b  sub     rsp, rax
0x14001b14e  mov     rax, cs:__security_cookie
0x14001b155  xor     rax, rsp
0x14001b158  mov     [rbp+1000h+var_40], rax
0x14001b15f  xor     r15d, r15d
0x14001b162  mov     word ptr [rbp+1000h+var_5C0], r15w
0x14001b16a  mov     ebx, 576h
0x14001b16f  mov     r8d, ebx; Size
0x14001b172  xor     edx, edx; Val
0x14001b174  lea     rcx, [rbp+1000h+var_5C0+2]; void *
0x14001b17b  call    memset_0
0x14001b180  mov     [rbp+1000h+var_B40], r15w
0x14001b188  mov     r8d, ebx; Size
0x14001b18b  xor     edx, edx; Val
0x14001b18d  lea     rcx, [rbp+1000h+var_B3E]; void *
0x14001b194  call    memset_0
0x14001b199  nop
0x14001b19a  mov     edi, r15d
0x14001b19d  mov     [rsp+1100h+lpName], r15; lpName
0x14001b1a2  mov     ebx, 208h
0x14001b1a7  mov     [rsp+1100h+dwMaximumSizeLow], ebx; dwMaximumSizeLow
0x14001b1ab  xor     r9d, r9d; dwMaximumSizeHigh
0x14001b1ae  xor     edx, edx; lpFileMappingAttributes
0x14001b1b0  lea     r8d, [r15+4]; flProtect
0x14001b1b4  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x14001b1b8  call    cs:__imp_CreateFileMappingW
0x14001b1be  mov     rsi, rax
0x14001b1c1  mov     [rsp+1100h+var_10D0], rax
0x14001b1c6  lea     r14, [rax+1]
0x14001b1ca  cmp     r14, 1
0x14001b1ce  jbe     loc_14001B41C
0x14001b1d4  mov     qword ptr [rsp+1100h+dwMaximumSizeLow], rbx; dwNumberOfBytesToMap
0x14001b1d9  xor     r9d, r9d; dwFileOffsetLow
0x14001b1dc  xor     r8d, r8d; dwFileOffsetHigh
0x14001b1df  mov     edx, 120116h; dwDesiredAccess
0x14001b1e4  mov     rcx, rax; hFileMappingObject
0x14001b1e7  call    cs:__imp_MapViewOfFile
0x14001b1ed  mov     rdi, rax
0x14001b1f0  mov     [rsp+1100h+var_10C8], rax
0x14001b1f5  test    rax, rax
0x14001b1f8  jz      loc_14001B405
0x14001b1fe  mov     eax, 7FFFFFFEh
0x14001b203  lea     rcx, aKLcq; "-k -lcq"
0x14001b20a  mov     edx, 104h
0x14001b20f  mov     r8, rdi
0x14001b212  test    rax, rax
0x14001b215  jz      short loc_14001B236
0x14001b217  movzx   r9d, word ptr [rcx]
0x14001b21b  test    r9w, r9w
0x14001b21f  jz      short loc_14001B236
0x14001b221  add     rcx, 2
0x14001b225  mov     [r8], r9w
0x14001b229  add     r8, 2
0x14001b22d  dec     rax
0x14001b230  sub     rdx, 1
0x14001b234  jnz     short loc_14001B212
0x14001b236  mov     rax, rdx
0x14001b239  neg     rax
0x14001b23c  sbb     ebx, ebx
0x14001b23e  not     ebx
0x14001b240  and     ebx, 8007007Ah
0x14001b246  lea     rcx, [r8-2]
0x14001b24a  test    rdx, rdx
0x14001b24d  cmovnz  rcx, r8
0x14001b251  mov     [rcx], r15w
0x14001b255  jnz     short loc_14001B282
0x14001b257  lea     rax, WPP_GLOBAL_Control
0x14001b25e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b265  cmp     rcx, rax
0x14001b268  jz      loc_14001B463
0x14001b26e  test    byte ptr [rcx+1Ch], 1
0x14001b272  jz      loc_14001B463
0x14001b278  mov     edx, 21h ; '!'
0x14001b27d  jmp     loc_14001B44F
0x14001b282  mov     ebx, 578h
0x14001b287  mov     r8d, ebx; Size
0x14001b28a  xor     edx, edx; Val
0x14001b28c  lea     rcx, [rsp+1100h+Src]; void *
0x14001b291  call    memset_0
0x14001b296  lea     rcx, [rbp+1000h+var_5C0]; void *
0x14001b29d  lea     rdx, [rsp+1100h+Src]; Src
0x14001b2a2  mov     r8d, ebx; Size
0x14001b2a5  call    memcpy_0
0x14001b2aa  mov     [rbp+1000h+var_5C0], 5780550h
0x14001b2b4  mov     [rbp+1000h+var_598], 50000000h
0x14001b2be  mov     [rbp+1000h+var_590], 1
0x14001b2c8  mov     eax, esi
0x14001b2ca  mov     [rbp+1000h+var_588], rax
0x14001b2d1  mov     [rbp+1000h+var_500], r15d
0x14001b2d8  lea     r8, [rbp+1000h+var_B40]; struct _WERSVC_MSG *
0x14001b2df  lea     rdx, [rbp+1000h+var_5C0]; struct _WERSVC_MSG *
0x14001b2e6  call    ?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x14001b2eb  mov     ecx, eax; Status
0x14001b2ed  call    cs:__imp_RtlNtStatusToDosError
0x14001b2f3  mov     ebx, eax
0x14001b2f5  test    eax, eax
0x14001b2f7  jle     short loc_14001B302
0x14001b2f9  movzx   ebx, ax
0x14001b2fc  or      ebx, 80070000h
0x14001b302  test    ebx, ebx
0x14001b304  jns     short loc_14001B331
0x14001b306  lea     rax, WPP_GLOBAL_Control
0x14001b30d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b314  cmp     rcx, rax
0x14001b317  jz      loc_14001B463
0x14001b31d  test    byte ptr [rcx+1Ch], 1
0x14001b321  jz      loc_14001B463
0x14001b327  mov     edx, 23h ; '#'
0x14001b32c  jmp     loc_14001B44F
0x14001b331  mov     eax, [rbp+1000h+var_B18]
0x14001b337  sub     eax, 50000001h
0x14001b33c  jz      short loc_14001B3B8
0x14001b33e  cmp     eax, 1
0x14001b341  jz      short loc_14001B383
0x14001b343  mov     ebx, 80004005h
0x14001b348  lea     rax, WPP_GLOBAL_Control
0x14001b34f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b356  cmp     rcx, rax
0x14001b359  jz      loc_14001B463
0x14001b35f  test    byte ptr [rcx+1Ch], 1
0x14001b363  jz      loc_14001B463
0x14001b369  mov     edx, 26h ; '&'
0x14001b36e  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001b375  mov     rcx, [rcx+10h]
0x14001b379  call    WPP_SF_
0x14001b37e  jmp     loc_14001B463
0x14001b383  mov     ebx, [rbp+1000h+var_B14]
0x14001b389  bts     ebx, 1Ch
0x14001b38d  lea     rax, WPP_GLOBAL_Control
0x14001b394  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b39b  cmp     rcx, rax
0x14001b39e  jz      loc_14001B463
0x14001b3a4  test    byte ptr [rcx+1Ch], 1
0x14001b3a8  jz      loc_14001B463
0x14001b3ae  mov     edx, 25h ; '%'
0x14001b3b3  jmp     loc_14001B44F
0x14001b3b8  mov     rbx, [rbp+1000h+hObject]
0x14001b3bf  lea     rax, WPP_GLOBAL_Control
0x14001b3c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b3cd  cmp     rcx, rax
0x14001b3d0  jz      short loc_14001B3ED
0x14001b3d2  test    byte ptr [rcx+1Ch], 4
0x14001b3d6  jz      short loc_14001B3ED
0x14001b3d8  mov     edx, 24h ; '$'
0x14001b3dd  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001b3e4  mov     rcx, [rcx+10h]
0x14001b3e8  call    WPP_SF_
0x14001b3ed  lea     rax, [rbx+1]
0x14001b3f1  cmp     rax, 1
0x14001b3f5  jbe     short loc_14001B400
0x14001b3f7  mov     rcx, rbx; hObject
0x14001b3fa  call    cs:__imp_CloseHandle
0x14001b400  mov     ebx, r15d
0x14001b403  jmp     short loc_14001B463
0x14001b405  call    cs:__imp_GetLastError
0x14001b40b  mov     ebx, eax
0x14001b40d  test    eax, eax
0x14001b40f  jle     short loc_14001B463
0x14001b411  movzx   ebx, ax
0x14001b414  or      ebx, 80070000h
0x14001b41a  jmp     short loc_14001B463
0x14001b41c  call    cs:__imp_GetLastError
0x14001b422  mov     ebx, eax
0x14001b424  test    eax, eax
0x14001b426  jle     short loc_14001B431
0x14001b428  movzx   ebx, ax
0x14001b42b  or      ebx, 80070000h
0x14001b431  lea     rax, WPP_GLOBAL_Control
0x14001b438  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b43f  cmp     rcx, rax
0x14001b442  jz      short loc_14001B463
0x14001b444  test    byte ptr [rcx+1Ch], 1
0x14001b448  jz      short loc_14001B463
0x14001b44a  mov     edx, 20h ; ' '
0x14001b44f  mov     r9d, ebx
0x14001b452  lea     r8, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x14001b459  mov     rcx, [rcx+10h]
0x14001b45d  call    WPP_SF_d
0x14001b462  nop
0x14001b463  test    rdi, rdi
0x14001b466  jz      short loc_14001B472
0x14001b468  mov     rcx, rdi; lpBaseAddress
0x14001b46b  call    cs:__imp_UnmapViewOfFile
0x14001b471  nop
0x14001b472  cmp     r14, 1
0x14001b476  jbe     short loc_14001B481
0x14001b478  mov     rcx, rsi; hObject
0x14001b47b  call    cs:__imp_CloseHandle
0x14001b481  mov     eax, ebx
0x14001b483  mov     rcx, [rbp+1000h+var_40]
0x14001b48a  xor     rcx, rsp; StackCookie
0x14001b48d  call    __security_check_cookie
0x14001b492  add     rsp, 10D8h
0x14001b499  pop     r15
0x14001b49b  pop     r14
0x14001b49d  pop     rdi
0x14001b49e  pop     rsi
0x14001b49f  pop     rbx
0x14001b4a0  pop     rbp
0x14001b4a1  retn
```
