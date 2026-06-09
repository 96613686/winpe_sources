# CreateTiffFileForJob(_JOB_QUEUE *)

- ea: `0x1400306e0`
- end: `0x1400308a9`
- name: `?CreateTiffFileForJob@@YAHPEAU_JOB_QUEUE@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(struct _JOB_QUEUE *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400311d0`
- `0x140032e04`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140030254`
- `0x1400306e0`
- `0x140037184`
- `0x14006af2c`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14003077d`
- `KERNEL32!GetLastError` at `0x1400307c6`
- `KERNEL32!GetLastError` at `0x140030831`
- `KERNEL32!GetLastError` at `0x14003077d`
- `KERNEL32!GetLastError` at `0x1400307c6`
- `KERNEL32!GetLastError` at `0x140030831`
- `KERNEL32!SetLastError` at `0x14003086d`
- `KERNEL32!SetLastError` at `0x14003086d`
- `KERNEL32!DeleteFileW` at `0x140030809`
- `KERNEL32!DeleteFileW` at `0x140030809`

## pseudocode

```c
__int64 __fastcall CreateTiffFileForJob(struct _JOB_QUEUE *a1)
{
  DWORD LastError; // eax
  __int64 v4; // rax
  DWORD v5; // eax
  DWORD v6; // ebx
  char v7; // al
  WCHAR FileName[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  memset_0(FileName, 0, 0x208u);
  if ( !(unsigned int)CreateTiffFile(a1, L"FRT", FileName) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, LastError);
    }
    return 0;
  }
  v4 = StringDup(FileName);
  *((_QWORD *)a1 + 9) = v4;
  if ( !v4 )
  {
    v5 = GetLastError();
    v6 = v5;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v5);
    }
    if ( !DeleteFileW(FileName)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = GetLastError();
      WPP_SF_lSl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
        *((_DWORD *)a1 + 8),
        (__int64)FileName,
        v7);
    }
    SetLastError(v6);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1400306e0  mov     [rsp+arg_8], rbx
0x1400306e5  mov     [rsp+arg_10], rbp
0x1400306ea  push    rdi
0x1400306eb  sub     rsp, 250h
0x1400306f2  mov     rax, cs:__security_cookie
0x1400306f9  xor     rax, rsp
0x1400306fc  mov     [rsp+258h+var_18], rax
0x140030704  mov     rdi, rcx
0x140030707  mov     rcx, cs:WPP_GLOBAL_Control
0x14003070e  lea     rbp, WPP_GLOBAL_Control
0x140030715  cmp     rcx, rbp
0x140030718  jz      short loc_14003073B
0x14003071a  test    byte ptr [rcx+1Ch], 4
0x14003071e  jz      short loc_14003073B
0x140030720  cmp     byte ptr [rcx+19h], 5
0x140030724  jb      short loc_14003073B
0x140030726  mov     rcx, [rcx+10h]
0x14003072a  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140030731  mov     edx, 38h ; '8'
0x140030736  call    WPP_SF_
0x14003073b  xor     edx, edx; Val
0x14003073d  lea     rcx, [rsp+258h+FileName]; void *
0x140030742  mov     r8d, 208h; Size
0x140030748  call    memset_0
0x14003074d  lea     r8, [rsp+258h+FileName]; unsigned __int16 *
0x140030752  mov     rcx, rdi; struct _JOB_QUEUE *
0x140030755  lea     rdx, aFrt; "FRT"
0x14003075c  call    ?CreateTiffFile@@YAHPEAU_JOB_QUEUE@@PEBGPEAGK@Z; CreateTiffFile(_JOB_QUEUE *,ushort const *,ushort *,ulong)
0x140030761  test    eax, eax
0x140030763  jnz     short loc_1400307AF
0x140030765  mov     rax, cs:WPP_GLOBAL_Control
0x14003076c  cmp     rax, rbp
0x14003076f  jz      short loc_1400307A8
0x140030771  test    byte ptr [rax+1Ch], 4
0x140030775  jz      short loc_1400307A8
0x140030777  cmp     byte ptr [rax+19h], 2
0x14003077b  jb      short loc_1400307A8
0x14003077d  call    cs:__imp_GetLastError
0x140030784  nop     dword ptr [rax+rax+00h]
0x140030789  mov     rcx, cs:WPP_GLOBAL_Control
0x140030790  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x140030797  mov     edx, 39h ; '9'
0x14003079c  mov     r9d, eax
0x14003079f  mov     rcx, [rcx+10h]
0x1400307a3  call    WPP_SF_d
0x1400307a8  xor     eax, eax
0x1400307aa  jmp     loc_140030883
0x1400307af  lea     rcx, [rsp+258h+FileName]; unsigned __int16 *
0x1400307b4  call    StringDup
0x1400307b9  mov     [rdi+48h], rax
0x1400307bd  test    rax, rax
0x1400307c0  jnz     loc_14003087E
0x1400307c6  call    cs:__imp_GetLastError
0x1400307cd  nop     dword ptr [rax+rax+00h]
0x1400307d2  mov     ebx, eax
0x1400307d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400307db  cmp     rcx, rbp
0x1400307de  jz      short loc_140030804
0x1400307e0  test    byte ptr [rcx+1Ch], 4
0x1400307e4  jz      short loc_140030804
0x1400307e6  cmp     byte ptr [rcx+19h], 2
0x1400307ea  jb      short loc_140030804
0x1400307ec  mov     rcx, [rcx+10h]
0x1400307f0  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400307f7  mov     edx, 3Ah ; ':'
0x1400307fc  mov     r9d, eax
0x1400307ff  call    WPP_SF_d
0x140030804  lea     rcx, [rsp+258h+FileName]; lpFileName
0x140030809  call    cs:__imp_DeleteFileW
0x140030810  nop     dword ptr [rax+rax+00h]
0x140030815  test    eax, eax
0x140030817  jnz     short loc_14003086B
0x140030819  mov     rax, cs:WPP_GLOBAL_Control
0x140030820  cmp     rax, rbp
0x140030823  jz      short loc_14003086B
0x140030825  test    byte ptr [rax+1Ch], 4
0x140030829  jz      short loc_14003086B
0x14003082b  cmp     byte ptr [rax+19h], 2
0x14003082f  jb      short loc_14003086B
0x140030831  call    cs:__imp_GetLastError
0x140030838  nop     dword ptr [rax+rax+00h]
0x14003083d  mov     rcx, cs:WPP_GLOBAL_Control
0x140030844  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14003084b  mov     r9d, [rdi+20h]
0x14003084f  mov     edx, 3Bh ; ';'
0x140030854  mov     [rsp+258h+var_230], eax
0x140030858  lea     rax, [rsp+258h+FileName]
0x14003085d  mov     [rsp+258h+var_238], rax
0x140030862  mov     rcx, [rcx+10h]
0x140030866  call    WPP_SF_lSl
0x14003086b  mov     ecx, ebx; dwErrCode
0x14003086d  call    cs:__imp_SetLastError
0x140030874  nop     dword ptr [rax+rax+00h]
0x140030879  jmp     loc_1400307A8
0x14003087e  mov     eax, 1
0x140030883  mov     rcx, [rsp+258h+var_18]
0x14003088b  xor     rcx, rsp; StackCookie
0x14003088e  call    __security_check_cookie
0x140030893  lea     r11, [rsp+258h+var_8]
0x14003089b  mov     rbx, [r11+18h]
0x14003089f  mov     rbp, [r11+20h]
0x1400308a3  mov     rsp, r11
0x1400308a6  pop     rdi
0x1400308a7  retn
```
