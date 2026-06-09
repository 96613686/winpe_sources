# CreateTiffFileForPreview(_JOB_QUEUE *)

- ea: `0x1400308b0`
- end: `0x140030a8a`
- name: `?CreateTiffFileForPreview@@YAHPEAU_JOB_QUEUE@@@Z`
- size: `474`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140010828`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140030254`
- `0x1400308b0`
- `0x140037184`
- `0x14006af2c`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003095b`
- `KERNEL32!GetLastError` at `0x1400309a7`
- `KERNEL32!GetLastError` at `0x140030a12`
- `KERNEL32!GetLastError` at `0x14003095b`
- `KERNEL32!GetLastError` at `0x1400309a7`
- `KERNEL32!GetLastError` at `0x140030a12`
- `KERNEL32!SetLastError` at `0x140030a4e`
- `KERNEL32!SetLastError` at `0x140030a4e`
- `KERNEL32!DeleteFileW` at `0x1400309ea`
- `KERNEL32!DeleteFileW` at `0x1400309ea`

## pseudocode

```c
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
0x1400308b0  mov     [rsp+arg_8], rbx
0x1400308b5  mov     [rsp+arg_10], rbp
0x1400308ba  push    rdi
0x1400308bb  sub     rsp, 250h
0x1400308c2  mov     rax, cs:__security_cookie
0x1400308c9  xor     rax, rsp
0x1400308cc  mov     [rsp+258h+var_18], rax
0x1400308d4  mov     rbx, rcx
0x1400308d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400308de  lea     rbp, WPP_GLOBAL_Control
0x1400308e5  cmp     rcx, rbp
0x1400308e8  jz      short loc_14003090B
0x1400308ea  test    byte ptr [rcx+1Ch], 4
0x1400308ee  jz      short loc_14003090B
0x1400308f0  cmp     byte ptr [rcx+19h], 5
0x1400308f4  jb      short loc_14003090B
0x1400308f6  mov     rcx, [rcx+10h]
0x1400308fa  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140030901  mov     edx, 3Ch ; '<'
0x140030906  call    WPP_SF_
0x14003090b  xor     edx, edx; Val
0x14003090d  lea     rcx, [rsp+258h+FileName]; void *
0x140030912  mov     r8d, 208h; Size
0x140030918  call    memset_0
0x14003091d  cmp     qword ptr [rbx+258h], 0
0x140030925  jnz     loc_140030A5F
0x14003092b  lea     r8, [rsp+258h+FileName]; unsigned __int16 *
0x140030930  mov     rcx, rbx; struct _JOB_QUEUE *
0x140030933  lea     rdx, aPrv; "PRV"
0x14003093a  call    ?CreateTiffFile@@YAHPEAU_JOB_QUEUE@@PEBGPEAGK@Z; CreateTiffFile(_JOB_QUEUE *,ushort const *,ushort *,ulong)
0x14003093f  test    eax, eax
0x140030941  jnz     short loc_14003098D
0x140030943  mov     rax, cs:WPP_GLOBAL_Control
0x14003094a  cmp     rax, rbp
0x14003094d  jz      short loc_140030986
0x14003094f  test    byte ptr [rax+1Ch], 4
0x140030953  jz      short loc_140030986
0x140030955  cmp     byte ptr [rax+19h], 2
0x140030959  jb      short loc_140030986
0x14003095b  call    cs:__imp_GetLastError
0x140030962  nop     dword ptr [rax+rax+00h]
0x140030967  mov     rcx, cs:WPP_GLOBAL_Control
0x14003096e  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140030975  mov     edx, 3Dh ; '='
0x14003097a  mov     r9d, eax
0x14003097d  mov     rcx, [rcx+10h]
0x140030981  call    WPP_SF_d
0x140030986  xor     eax, eax
0x140030988  jmp     loc_140030A64
0x14003098d  lea     rcx, [rsp+258h+FileName]; unsigned __int16 *
0x140030992  call    StringDup
0x140030997  mov     [rbx+258h], rax
0x14003099e  test    rax, rax
0x1400309a1  jnz     loc_140030A5F
0x1400309a7  call    cs:__imp_GetLastError
0x1400309ae  nop     dword ptr [rax+rax+00h]
0x1400309b3  mov     edi, eax
0x1400309b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400309bc  cmp     rcx, rbp
0x1400309bf  jz      short loc_1400309E5
0x1400309c1  test    byte ptr [rcx+1Ch], 4
0x1400309c5  jz      short loc_1400309E5
0x1400309c7  cmp     byte ptr [rcx+19h], 2
0x1400309cb  jb      short loc_1400309E5
0x1400309cd  mov     rcx, [rcx+10h]
0x1400309d1  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400309d8  mov     edx, 3Eh ; '>'
0x1400309dd  mov     r9d, eax
0x1400309e0  call    WPP_SF_d
0x1400309e5  lea     rcx, [rsp+258h+FileName]; lpFileName
0x1400309ea  call    cs:__imp_DeleteFileW
0x1400309f1  nop     dword ptr [rax+rax+00h]
0x1400309f6  test    eax, eax
0x1400309f8  jnz     short loc_140030A4C
0x1400309fa  mov     rax, cs:WPP_GLOBAL_Control
0x140030a01  cmp     rax, rbp
0x140030a04  jz      short loc_140030A4C
0x140030a06  test    byte ptr [rax+1Ch], 4
0x140030a0a  jz      short loc_140030A4C
0x140030a0c  cmp     byte ptr [rax+19h], 2
0x140030a10  jb      short loc_140030A4C
0x140030a12  call    cs:__imp_GetLastError
0x140030a19  nop     dword ptr [rax+rax+00h]
0x140030a1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140030a25  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140030a2c  mov     r9d, [rbx+20h]
0x140030a30  mov     edx, 3Fh ; '?'
0x140030a35  mov     [rsp+258h+var_230], eax
0x140030a39  lea     rax, [rsp+258h+FileName]
0x140030a3e  mov     [rsp+258h+var_238], rax
0x140030a43  mov     rcx, [rcx+10h]
0x140030a47  call    WPP_SF_lSl
0x140030a4c  mov     ecx, edi; dwErrCode
0x140030a4e  call    cs:__imp_SetLastError
0x140030a55  nop     dword ptr [rax+rax+00h]
0x140030a5a  jmp     loc_140030986
0x140030a5f  mov     eax, 1
0x140030a64  mov     rcx, [rsp+258h+var_18]
0x140030a6c  xor     rcx, rsp; StackCookie
0x140030a6f  call    __security_check_cookie
0x140030a74  lea     r11, [rsp+258h+var_8]
0x140030a7c  mov     rbx, [r11+18h]
0x140030a80  mov     rbp, [r11+20h]
0x140030a84  mov     rsp, r11
0x140030a87  pop     rdi
0x140030a88  retn
```
