# CreateTiffFileForPreview(_JOB_QUEUE *)

- ea: `0x14002f168`
- end: `0x14002f323`
- name: `?CreateTiffFileForPreview@@YAHPEAU_JOB_QUEUE@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140010150`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x14002eb78`
- `0x14002f168`
- `0x1400354bc`
- `0x140067168`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002f213`
- `KERNEL32!GetLastError` at `0x14002f259`
- `KERNEL32!GetLastError` at `0x14002f2b8`
- `KERNEL32!GetLastError` at `0x14002f213`
- `KERNEL32!GetLastError` at `0x14002f259`
- `KERNEL32!GetLastError` at `0x14002f2b8`
- `KERNEL32!SetLastError` at `0x14002f2ee`
- `KERNEL32!SetLastError` at `0x14002f2ee`
- `KERNEL32!DeleteFileW` at `0x14002f296`
- `KERNEL32!DeleteFileW` at `0x14002f296`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CreateTiffFileForPreview(struct _JOB_QUEUE *a1)
{
  DWORD LastError; // eax
  __int64 v4; // rax
  DWORD v5; // eax
  DWORD v6; // edi
  char v7; // al
  WCHAR FileName[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  memset_0(FileName, 0, 0x208u);
  if ( !*((_QWORD *)a1 + 75) )
  {
    if ( !(unsigned int)CreateTiffFile(a1, L"PRV", FileName) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, LastError);
      }
      return 0;
    }
    v4 = StringDup(FileName);
    *((_QWORD *)a1 + 75) = v4;
    if ( !v4 )
    {
      v5 = GetLastError();
      v6 = v5;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v5);
      }
      if ( !DeleteFileW(FileName)
        && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = GetLastError();
        WPP_SF_lSl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          63,
          (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
          *((_DWORD *)a1 + 8),
          (__int64)FileName,
          v7);
      }
      SetLastError(v6);
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14002f168  mov     [rsp+arg_8], rbx
0x14002f16d  mov     [rsp+arg_10], rbp
0x14002f172  push    rdi
0x14002f173  sub     rsp, 250h
0x14002f17a  mov     rax, cs:__security_cookie
0x14002f181  xor     rax, rsp
0x14002f184  mov     [rsp+258h+var_18], rax
0x14002f18c  mov     rbx, rcx
0x14002f18f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f196  lea     rbp, WPP_GLOBAL_Control
0x14002f19d  cmp     rcx, rbp
0x14002f1a0  jz      short loc_14002F1C3
0x14002f1a2  test    byte ptr [rcx+1Ch], 4
0x14002f1a6  jz      short loc_14002F1C3
0x14002f1a8  cmp     byte ptr [rcx+19h], 5
0x14002f1ac  jb      short loc_14002F1C3
0x14002f1ae  mov     rcx, [rcx+10h]
0x14002f1b2  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f1b9  mov     edx, 3Ch ; '<'
0x14002f1be  call    WPP_SF_
0x14002f1c3  xor     edx, edx; Val
0x14002f1c5  lea     rcx, [rsp+258h+FileName]; void *
0x14002f1ca  mov     r8d, 208h; Size
0x14002f1d0  call    memset_0
0x14002f1d5  cmp     qword ptr [rbx+258h], 0
0x14002f1dd  jnz     loc_14002F2F9
0x14002f1e3  lea     r8, [rsp+258h+FileName]; unsigned __int16 *
0x14002f1e8  mov     rcx, rbx; struct _JOB_QUEUE *
0x14002f1eb  lea     rdx, aPrv; "PRV"
0x14002f1f2  call    ?CreateTiffFile@@YAHPEAU_JOB_QUEUE@@PEBGPEAGK@Z; CreateTiffFile(_JOB_QUEUE *,ushort const *,ushort *,ulong)
0x14002f1f7  test    eax, eax
0x14002f1f9  jnz     short loc_14002F23F
0x14002f1fb  mov     rax, cs:WPP_GLOBAL_Control
0x14002f202  cmp     rax, rbp
0x14002f205  jz      short loc_14002F238
0x14002f207  test    byte ptr [rax+1Ch], 4
0x14002f20b  jz      short loc_14002F238
0x14002f20d  cmp     byte ptr [rax+19h], 2
0x14002f211  jb      short loc_14002F238
0x14002f213  call    cs:__imp_GetLastError
0x14002f219  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f220  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f227  mov     edx, 3Dh ; '='
0x14002f22c  mov     r9d, eax
0x14002f22f  mov     rcx, [rcx+10h]
0x14002f233  call    WPP_SF_d
0x14002f238  xor     eax, eax
0x14002f23a  jmp     loc_14002F2FE
0x14002f23f  lea     rcx, [rsp+258h+FileName]; unsigned __int16 *
0x14002f244  call    StringDup
0x14002f249  mov     [rbx+258h], rax
0x14002f250  test    rax, rax
0x14002f253  jnz     loc_14002F2F9
0x14002f259  call    cs:__imp_GetLastError
0x14002f25f  mov     edi, eax
0x14002f261  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f268  cmp     rcx, rbp
0x14002f26b  jz      short loc_14002F291
0x14002f26d  test    byte ptr [rcx+1Ch], 4
0x14002f271  jz      short loc_14002F291
0x14002f273  cmp     byte ptr [rcx+19h], 2
0x14002f277  jb      short loc_14002F291
0x14002f279  mov     rcx, [rcx+10h]
0x14002f27d  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f284  mov     edx, 3Eh ; '>'
0x14002f289  mov     r9d, eax
0x14002f28c  call    WPP_SF_d
0x14002f291  lea     rcx, [rsp+258h+FileName]; lpFileName
0x14002f296  call    cs:__imp_DeleteFileW
0x14002f29c  test    eax, eax
0x14002f29e  jnz     short loc_14002F2EC
0x14002f2a0  mov     rax, cs:WPP_GLOBAL_Control
0x14002f2a7  cmp     rax, rbp
0x14002f2aa  jz      short loc_14002F2EC
0x14002f2ac  test    byte ptr [rax+1Ch], 4
0x14002f2b0  jz      short loc_14002F2EC
0x14002f2b2  cmp     byte ptr [rax+19h], 2
0x14002f2b6  jb      short loc_14002F2EC
0x14002f2b8  call    cs:__imp_GetLastError
0x14002f2be  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f2c5  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002f2cc  mov     r9d, [rbx+20h]
0x14002f2d0  mov     edx, 3Fh ; '?'
0x14002f2d5  mov     [rsp+258h+var_230], eax
0x14002f2d9  lea     rax, [rsp+258h+FileName]
0x14002f2de  mov     [rsp+258h+var_238], rax
0x14002f2e3  mov     rcx, [rcx+10h]
0x14002f2e7  call    WPP_SF_lSl
0x14002f2ec  mov     ecx, edi; dwErrCode
0x14002f2ee  call    cs:__imp_SetLastError
0x14002f2f4  jmp     loc_14002F238
0x14002f2f9  mov     eax, 1
0x14002f2fe  mov     rcx, [rsp+258h+var_18]
0x14002f306  xor     rcx, rsp; StackCookie
0x14002f309  call    __security_check_cookie
0x14002f30e  lea     r11, [rsp+258h+var_8]
0x14002f316  mov     rbx, [r11+18h]
0x14002f31a  mov     rbp, [r11+20h]
0x14002f31e  mov     rsp, r11
0x14002f321  pop     rdi
0x14002f322  retn
```
