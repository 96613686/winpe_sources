# UtilSetFileSecurity(wchar_t const *,ulong,void *)

- ea: `0x18000718c`
- end: `0x1800072c4`
- name: `?UtilSetFileSecurity@@YAJPEB_WKPEAX@Z`
- size: `312`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d128`

## callees

- `0x18000716c`
- `0x18000718c`
- `0x1800072cc`
- `0x180014720`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000725b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000725b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072a9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800072a9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800071c6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800071c6`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180007251`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180007251`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilSetFileSecurity(WCHAR *a1, __int64 a2, void *a3)
{
  HANDLE FileW; // rax
  void *v6; // rdi
  unsigned __int64 v7; // r14
  DWORD v8; // eax
  int v9; // ebx
  wchar_t *v10; // rcx
  int v11; // edx
  DWORD LastError; // eax

  FileW = CreateFileW(a1, 0x60000u, 3u, 0, 3u, 0x2200080u, 0);
  v6 = FileW;
  v7 = (unsigned __int64)FileW + 1;
  if ( (unsigned __int64)FileW + 1 > 1 )
  {
    v9 = UtilVerifyFilePath(a1, FileW);
    if ( v9 >= 0 )
    {
      if ( !SetKernelObjectSecurity(v6, 4u, a3) )
      {
        LastError = GetLastError();
        v9 = ERROR_HR_FROM_WIN32(LastError);
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v11 = 16;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v11 = 15;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v8 = GetLastError();
    v9 = ERROR_HR_FROM_WIN32(v8);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 14;
LABEL_13:
      WPP_SF_SD(
        *((_QWORD *)v10 + 2),
        v11,
        (unsigned int)WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids,
        (_DWORD)a1,
        v9);
    }
  }
  if ( v7 > 1 )
    CloseHandle(v6);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000718c  mov     rax, rsp
0x18000718f  mov     [rax+8], rbx
0x180007193  mov     [rax+10h], rbp
0x180007197  push    rsi
0x180007198  push    rdi
0x180007199  push    r14
0x18000719b  sub     rsp, 40h
0x18000719f  mov     rbp, r8
0x1800071a2  mov     rsi, rcx
0x1800071a5  mov     qword ptr [rax-28h], 0
0x1800071ad  mov     dword ptr [rax-30h], 2200080h
0x1800071b4  mov     r8d, 3; dwShareMode
0x1800071ba  mov     [rax-38h], r8d
0x1800071be  xor     r9d, r9d; lpSecurityAttributes
0x1800071c1  mov     edx, 60000h; dwDesiredAccess
0x1800071c6  call    cs:__imp_CreateFileW
0x1800071cc  mov     rdi, rax
0x1800071cf  mov     [rsp+58h+arg_18], rax
0x1800071d4  lea     r14, [rax+1]
0x1800071d8  cmp     r14, 1
0x1800071dc  ja      short loc_180007215
0x1800071de  call    cs:__imp_GetLastError
0x1800071e4  mov     ecx, eax; unsigned int
0x1800071e6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800071eb  mov     ebx, eax
0x1800071ed  lea     rax, WPP_GLOBAL_Control
0x1800071f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071fb  cmp     rcx, rax
0x1800071fe  jz      loc_1800072A0
0x180007204  test    byte ptr [rcx+1Ch], 1
0x180007208  jz      loc_1800072A0
0x18000720e  mov     edx, 0Eh
0x180007213  jmp     short loc_180007288
0x180007215  mov     rdx, rdi; void *
0x180007218  mov     rcx, rsi; wchar_t *
0x18000721b  call    ?UtilVerifyFilePath@@YAJPEB_WPEAX@Z; UtilVerifyFilePath(wchar_t const *,void *)
0x180007220  mov     ebx, eax
0x180007222  test    eax, eax
0x180007224  jns     short loc_180007246
0x180007226  lea     rax, WPP_GLOBAL_Control
0x18000722d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007234  cmp     rcx, rax
0x180007237  jz      short loc_1800072A0
0x180007239  test    byte ptr [rcx+1Ch], 1
0x18000723d  jz      short loc_1800072A0
0x18000723f  mov     edx, 0Fh
0x180007244  jmp     short loc_180007288
0x180007246  mov     r8, rbp; SecurityDescriptor
0x180007249  mov     edx, 4; SecurityInformation
0x18000724e  mov     rcx, rdi; Handle
0x180007251  call    cs:__imp_SetKernelObjectSecurity
0x180007257  test    eax, eax
0x180007259  jnz     short loc_1800072A0
0x18000725b  call    cs:__imp_GetLastError
0x180007261  mov     ecx, eax; unsigned int
0x180007263  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180007268  mov     ebx, eax
0x18000726a  lea     rax, WPP_GLOBAL_Control
0x180007271  mov     rcx, cs:WPP_GLOBAL_Control
0x180007278  cmp     rcx, rax
0x18000727b  jz      short loc_1800072A0
0x18000727d  test    byte ptr [rcx+1Ch], 1
0x180007281  jz      short loc_1800072A0
0x180007283  mov     edx, 10h
0x180007288  mov     [rsp+58h+var_38], ebx
0x18000728c  mov     r9, rsi
0x18000728f  lea     r8, WPP_69e296c8cfbe35481aeff25676a4a37b_Traceguids
0x180007296  mov     rcx, [rcx+10h]
0x18000729a  call    WPP_SF_SD
0x18000729f  nop
0x1800072a0  cmp     r14, 1
0x1800072a4  jbe     short loc_1800072AF
0x1800072a6  mov     rcx, rdi; hObject
0x1800072a9  call    cs:__imp_CloseHandle
0x1800072af  mov     eax, ebx
0x1800072b1  mov     rbx, [rsp+58h+arg_0]
0x1800072b6  mov     rbp, [rsp+58h+arg_8]
0x1800072bb  add     rsp, 40h
0x1800072bf  pop     r14
0x1800072c1  pop     rdi
0x1800072c2  pop     rsi
0x1800072c3  retn
```
