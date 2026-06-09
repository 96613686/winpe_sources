# WriteAndReplaceFile(std::unique_ptr<void *,release::Deleter<release::handle_tag>> &,std::unique_ptr<ushort,release::Deleter<release::delete_file_tag>> &,ushort const (&)[261],void const *,ulong)

- ea: `0x140006000`
- end: `0x14000614b`
- name: `?WriteAndReplaceFile@@YAKAEAV?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAV?$unique_ptr@GU?$Deleter@Udelete_file_tag@release@@@release@@@2@AEAY0BAF@$$CBGPEBXK@Z`
- size: `331`
- prototype: `__int64 __fastcall(HANDLE **, LPCWSTR *, const WCHAR *, const void *, DWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140006154`
- `0x1400064f8`

## callees

- `0x140006000`
- `0x140007010`
- `0x1400072ec`
- `0x1400073a8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140006030`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140006030`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140006080`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x140006080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000603a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000608a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000603a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000608a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400060dc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400060ee`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400060ee`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400060d2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1400060d2`

## pseudocode

```c
__int64 __fastcall WriteAndReplaceFile(HANDLE **a1, LPCWSTR *a2, const WCHAR *a3, const void *a4, DWORD a5)
{
  DWORD LastError; // edi
  int v9; // r8d
  _QWORD *v10; // rcx
  int v11; // edx
  unsigned int i; // esi
  int v14; // r8d

  if ( !WriteFile(**a1, a4, a5, &a5, 0) )
  {
    LastError = GetLastError();
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      return LastError;
    v11 = 55;
    goto LABEL_5;
  }
  if ( !FlushFileBuffers(**a1) )
  {
    LastError = GetLastError();
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      return LastError;
    v11 = 56;
LABEL_5:
    WPP_SF_Sd(v10[2], v11, v9, (unsigned int)*a2, LastError);
    return LastError;
  }
  std::unique_ptr<void *,release::Deleter<release::handle_tag>>::reset(a1, 0);
  for ( i = 0; ; ++i )
  {
    if ( i >= 0xA )
      return 0;
    if ( MoveFileExW(*a2, a3, 1u) )
    {
      *a2 = 0;
      return 0;
    }
    LastError = GetLastError();
    if ( LastError != 32 )
      break;
    Sleep(0x3E8u);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_SSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      v14,
      (_DWORD)a3,
      (__int64)*a2,
      LastError);
  return LastError;
}

```

## disassembly

```asm
0x140006000  mov     r11, rsp
0x140006003  push    rbx
0x140006004  push    rbp
0x140006005  push    rsi
0x140006006  push    rdi
0x140006007  sub     rsp, 38h
0x14000600b  mov     rdi, rcx
0x14000600e  mov     qword ptr [r11-38h], 0
0x140006016  mov     rcx, [rcx]
0x140006019  mov     rax, r9
0x14000601c  mov     rbp, r8
0x14000601f  lea     r9, [r11+28h]; lpNumberOfBytesWritten
0x140006023  mov     r8d, [r11+28h]; nNumberOfBytesToWrite
0x140006027  mov     rbx, rdx
0x14000602a  mov     rdx, rax; lpBuffer
0x14000602d  mov     rcx, [rcx]; hFile
0x140006030  call    cs:__imp_WriteFile
0x140006036  test    eax, eax
0x140006038  jnz     short loc_14000607A
0x14000603a  call    cs:__imp_GetLastError
0x140006040  mov     edi, eax
0x140006042  mov     rcx, cs:WPP_GLOBAL_Control
0x140006049  lea     rdx, WPP_GLOBAL_Control
0x140006050  cmp     rcx, rdx
0x140006053  jz      short loc_140006073
0x140006055  test    dword ptr [rcx+1Ch], 800h
0x14000605c  jz      short loc_140006073
0x14000605e  mov     edx, 37h ; '7'
0x140006063  mov     r9, [rbx]
0x140006066  mov     rcx, [rcx+10h]
0x14000606a  mov     dword ptr [rsp+58h+var_38], edi
0x14000606e  call    WPP_SF_Sd
0x140006073  mov     eax, edi
0x140006075  jmp     loc_140006142
0x14000607a  mov     rcx, [rdi]
0x14000607d  mov     rcx, [rcx]; hFile
0x140006080  call    cs:__imp_FlushFileBuffers
0x140006086  test    eax, eax
0x140006088  jnz     short loc_1400060B5
0x14000608a  call    cs:__imp_GetLastError
0x140006090  mov     edi, eax
0x140006092  mov     rcx, cs:WPP_GLOBAL_Control
0x140006099  lea     rdx, WPP_GLOBAL_Control
0x1400060a0  cmp     rcx, rdx
0x1400060a3  jz      short loc_140006073
0x1400060a5  test    dword ptr [rcx+1Ch], 800h
0x1400060ac  jz      short loc_140006073
0x1400060ae  mov     edx, 38h ; '8'
0x1400060b3  jmp     short loc_140006063
0x1400060b5  xor     edx, edx
0x1400060b7  mov     rcx, rdi
0x1400060ba  call    ?reset@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@QEAAXPEAPEAX@Z; std::unique_ptr<void *,release::Deleter<release::handle_tag>>::reset(void * *)
0x1400060bf  xor     esi, esi
0x1400060c1  cmp     esi, 0Ah
0x1400060c4  jnb     short loc_140006140
0x1400060c6  mov     rcx, [rbx]; lpExistingFileName
0x1400060c9  mov     r8d, 1; dwFlags
0x1400060cf  mov     rdx, rbp; lpNewFileName
0x1400060d2  call    cs:__imp_MoveFileExW
0x1400060d8  test    eax, eax
0x1400060da  jnz     short loc_140006139
0x1400060dc  call    cs:__imp_GetLastError
0x1400060e2  mov     edi, eax
0x1400060e4  cmp     eax, 20h ; ' '
0x1400060e7  jnz     short loc_1400060F8
0x1400060e9  mov     ecx, 3E8h; dwMilliseconds
0x1400060ee  call    cs:__imp_Sleep
0x1400060f4  inc     esi
0x1400060f6  jmp     short loc_1400060C1
0x1400060f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060ff  lea     rdx, WPP_GLOBAL_Control
0x140006106  cmp     rcx, rdx
0x140006109  jz      loc_140006073
0x14000610f  test    dword ptr [rcx+1Ch], 800h
0x140006116  jz      loc_140006073
0x14000611c  mov     rax, [rbx]
0x14000611f  mov     r9, rbp
0x140006122  mov     rcx, [rcx+10h]
0x140006126  mov     [rsp+58h+var_30], edi
0x14000612a  mov     [rsp+58h+var_38], rax
0x14000612f  call    WPP_SF_SSd
0x140006134  jmp     loc_140006073
0x140006139  mov     qword ptr [rbx], 0
0x140006140  xor     eax, eax
0x140006142  add     rsp, 38h
0x140006146  pop     rdi
0x140006147  pop     rsi
0x140006148  pop     rbp
0x140006149  pop     rbx
0x14000614a  retn
```
