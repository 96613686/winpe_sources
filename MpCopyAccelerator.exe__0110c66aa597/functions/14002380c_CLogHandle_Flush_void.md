# CLogHandle::Flush(void)

- ea: `0x14002380c`
- end: `0x140023b94`
- name: `?Flush@CLogHandle@@QEAAJXZ`
- size: `904`
- prototype: `__int64 __fastcall(CLogHandle *__hidden this)`
- caller_count: `6`
- callee_count: `14`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x14001d700`
- `0x14001f6a0`
- `0x14001fce0`
- `0x14001ffe0`
- `0x1400235e4`
- `0x140023ec8`

## callees

- `0x14000436c`
- `0x140004440`
- `0x140004740`
- `0x1400047e0`
- `0x140005264`
- `0x140005c20`
- `0x14001da4c`
- `0x14001da70`
- `0x14001dac4`
- `0x140020220`
- `0x140023664`
- `0x14002380c`
- `0x1400242c4`
- `0x140024570`

## import_xrefs

- `KERNEL32!Sleep` at `0x14002395d`
- `KERNEL32!Sleep` at `0x14002395d`
- `KERNEL32!CloseHandle` at `0x1400238d0`
- `KERNEL32!CloseHandle` at `0x1400239ad`
- `KERNEL32!CloseHandle` at `0x140023b2a`
- `KERNEL32!CloseHandle` at `0x140023b61`
- `KERNEL32!CloseHandle` at `0x1400238d0`
- `KERNEL32!CloseHandle` at `0x1400239ad`
- `KERNEL32!CloseHandle` at `0x140023b2a`
- `KERNEL32!CloseHandle` at `0x140023b61`

## pseudocode

```c
__int64 __fastcall CLogHandle::Flush(CLogHandle *this)
{
  char v3; // r13
  unsigned __int64 i; // r15
  int IsAReparsePoint; // r14d
  void **v6; // r14
  int File; // eax
  void *v8; // r8
  const void *v9; // r9
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  int v12; // edx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  const void *v15; // r9
  HANDLE v16; // rcx
  unsigned __int64 *v17; // [rsp+20h] [rbp-40h]
  HANDLE hObject; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v19; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-10h] BYREF

  if ( *((_QWORD *)this + 5) == *((_QWORD *)this + 3) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids);
    return 1;
  }
  v3 = *((_BYTE *)this + 48);
  hObject = (HANDLE)-1LL;
  *((_BYTE *)this + 48) = 1;
  for ( i = 0; ; ++i )
  {
    IsAReparsePoint = CLogHandle::CleanIfLogIsAReparsePoint(this);
    if ( IsAReparsePoint < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids);
      goto LABEL_51;
    }
    v6 = (void **)*((_QWORD *)this + 7);
    if ( hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    File = CommonUtil::UtilCreateFile(
             (CommonUtil *)&hObject,
             v6,
             (const wchar_t *)0x40000000,
             1u,
             v3 != 0 ? 4 : 2,
             0x80u,
             0,
             0,
             hObject);
    IsAReparsePoint = File;
    if ( File >= 0 )
      break;
    if ( File != -2147024864 || i >= 0xA )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_51;
      v12 = 14;
      goto LABEL_27;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids,
        *((_QWORD *)this + 7));
    Sleep(0x1F4u);
LABEL_23:
    ;
  }
  if ( i )
    goto LABEL_28;
  v20 = 0;
  IsAReparsePoint = CommonUtil::UtilGetFileSize((CommonUtil *)&v20, (unsigned __int64 *)hObject, v8);
  if ( IsAReparsePoint < 0 )
    goto LABEL_51;
  v10 = MpCommonConfigLookupDword(L"MpCmdRun_MaxLogSize", 0x1000000);
  if ( v20 >= v10 )
  {
    if ( hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    PurgeLog(*((wchar_t **)this + 7));
    goto LABEL_23;
  }
LABEL_28:
  if ( !v3 )
  {
    LOWORD(v19) = -257;
    IsAReparsePoint = CommonUtil::UtilWriteFile(hObject, (void *)2, (unsigned __int64)&v19, v9);
    if ( IsAReparsePoint < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = 15;
        goto LABEL_33;
      }
      goto LABEL_51;
    }
  }
  IsAReparsePoint = CommonUtil::UtilSetFilePointer((CommonUtil *)hObject, 0, 2u, 0, v17);
  if ( IsAReparsePoint < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_51;
    v12 = 16;
LABEL_27:
    WPP_SF_Sd(
      v11[2],
      v12,
      (unsigned int)&WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids,
      *((_QWORD *)this + 7),
      IsAReparsePoint);
    goto LABEL_51;
  }
  IsAReparsePoint = CommonUtil::UtilWriteFile(
                      hObject,
                      (void *)(2 * (unsigned int)((__int64)(*((_QWORD *)this + 4) - *((_QWORD *)this + 2)) >> 1)),
                      *((_QWORD *)this + 2),
                      v15);
  if ( IsAReparsePoint < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 17;
LABEL_33:
      WPP_SF_d(v13[2], v14, &WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids, (unsigned int)IsAReparsePoint);
    }
LABEL_51:
    if ( hObject != (HANDLE)-1LL )
      CloseHandle(hObject);
    return (unsigned int)IsAReparsePoint;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), *((_QWORD *)this + 7));
  v16 = hObject;
  *((_QWORD *)this + 5) = *((_QWORD *)this + 3);
  *((_QWORD *)this + 4) = *((_QWORD *)this + 2);
  if ( v16 != (HANDLE)-1LL )
    CloseHandle(v16);
  return 0;
}

```

## disassembly

```asm
0x14002380c  mov     [rsp-28h+arg_8], rbx
0x140023811  mov     [rsp-28h+arg_10], rsi
0x140023816  mov     [rsp-28h+arg_18], rdi
0x14002381b  push    rbp
0x14002381c  push    r12
0x14002381e  push    r13
0x140023820  push    r14
0x140023822  push    r15
0x140023824  mov     rbp, rsp
0x140023827  sub     rsp, 60h
0x14002382b  mov     rax, cs:__security_cookie
0x140023832  xor     rax, rsp
0x140023835  mov     [rbp+var_8], rax
0x140023839  mov     rax, [rcx+18h]
0x14002383d  mov     rbx, rcx
0x140023840  cmp     [rcx+28h], rax
0x140023844  jnz     short loc_14002387E
0x140023846  mov     rcx, cs:WPP_GLOBAL_Control
0x14002384d  lea     rdi, WPP_GLOBAL_Control
0x140023854  cmp     rcx, rdi
0x140023857  jz      short loc_140023874
0x140023859  test    byte ptr [rcx+1Ch], 4
0x14002385d  jz      short loc_140023874
0x14002385f  mov     rcx, [rcx+10h]
0x140023863  lea     r8, WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids
0x14002386a  mov     edx, 0Bh
0x14002386f  call    WPP_SF_
0x140023874  mov     eax, 1
0x140023879  jmp     loc_140023B6A
0x14002387e  mov     r13b, [rcx+30h]
0x140023882  lea     rdi, WPP_GLOBAL_Control
0x140023889  mov     al, r13b
0x14002388c  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x140023894  neg     al
0x140023896  mov     byte ptr [rcx+30h], 1
0x14002389a  lea     rsi, WPP_4c401faab9b1388d1fa6583bd2a81a5a_Traceguids
0x1400238a1  sbb     r12d, r12d
0x1400238a4  and     r12d, 2
0x1400238a8  add     r12d, 2
0x1400238ac  xor     r15d, r15d
0x1400238af  mov     rcx, rbx; this
0x1400238b2  call    ?CleanIfLogIsAReparsePoint@CLogHandle@@AEAAJXZ; CLogHandle::CleanIfLogIsAReparsePoint(void)
0x1400238b7  mov     r14d, eax
0x1400238ba  test    eax, eax
0x1400238bc  js      loc_140023B34
0x1400238c2  mov     rcx, [rbp+hObject]; hObject
0x1400238c6  mov     r14, [rbx+38h]
0x1400238ca  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400238ce  jz      short loc_1400238DE
0x1400238d0  call    cs:__imp_CloseHandle
0x1400238d6  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x1400238de  mov     [rsp+60h+var_28], 0; struct _SECURITY_ATTRIBUTES *
0x1400238e7  lea     rcx, [rbp+hObject]; this
0x1400238eb  mov     qword ptr [rsp+60h+var_30], 0; unsigned int
0x1400238f4  mov     r9d, 1; unsigned int
0x1400238fa  mov     [rsp+60h+var_38], 80h; unsigned int
0x140023902  mov     r8d, 40000000h; wchar_t *
0x140023908  mov     rdx, r14; void **
0x14002390b  mov     dword ptr [rsp+60h+var_40], r12d; unsigned __int64 *
0x140023910  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,wchar_t const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x140023915  mov     r14d, eax
0x140023918  test    eax, eax
0x14002391a  jns     short loc_140023965
0x14002391c  cmp     eax, 80070020h
0x140023921  jnz     loc_1400239CC
0x140023927  cmp     r15, 0Ah
0x14002392b  jnb     loc_1400239CC
0x140023931  mov     rcx, cs:WPP_GLOBAL_Control
0x140023938  cmp     rcx, rdi
0x14002393b  jz      short loc_140023958
0x14002393d  test    byte ptr [rcx+1Ch], 4
0x140023941  jz      short loc_140023958
0x140023943  mov     r9, [rbx+38h]
0x140023947  mov     edx, 0Dh
0x14002394c  mov     rcx, [rcx+10h]
0x140023950  mov     r8, rsi
0x140023953  call    WPP_SF_S
0x140023958  mov     ecx, 1F4h; dwMilliseconds
0x14002395d  call    cs:__imp_Sleep
0x140023963  jmp     short loc_1400239C4
0x140023965  test    r15, r15
0x140023968  jnz     loc_140023A05
0x14002396e  mov     rdx, [rbp+hObject]; unsigned __int64 *
0x140023972  lea     rcx, [rbp+var_10]; this
0x140023976  mov     [rbp+var_10], r15
0x14002397a  call    ?UtilGetFileSize@CommonUtil@@YAJPEA_KPEAX@Z; CommonUtil::UtilGetFileSize(unsigned __int64 *,void *)
0x14002397f  mov     r14d, eax
0x140023982  test    eax, eax
0x140023984  js      loc_140023B57
0x14002398a  mov     edx, 1000000h
0x14002398f  lea     rcx, aMpcmdrunMaxlog; "MpCmdRun_MaxLogSize"
0x140023996  call    MpCommonConfigLookupDword
0x14002399b  mov     eax, eax
0x14002399d  cmp     [rbp+var_10], rax
0x1400239a1  jb      short loc_140023A05
0x1400239a3  mov     rcx, [rbp+hObject]; hObject
0x1400239a7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400239ab  jz      short loc_1400239BB
0x1400239ad  call    cs:__imp_CloseHandle
0x1400239b3  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x1400239bb  mov     rcx, [rbx+38h]; wchar_t *
0x1400239bf  call    PurgeLog
0x1400239c4  inc     r15
0x1400239c7  jmp     loc_1400238AF
0x1400239cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400239d3  cmp     rcx, rdi
0x1400239d6  jz      loc_140023B57
0x1400239dc  test    byte ptr [rcx+1Ch], 1
0x1400239e0  jz      loc_140023B57
0x1400239e6  mov     edx, 0Eh
0x1400239eb  mov     r9, [rbx+38h]
0x1400239ef  mov     r8, rsi
0x1400239f2  mov     rcx, [rcx+10h]
0x1400239f6  mov     dword ptr [rsp+60h+var_40], r14d
0x1400239fb  call    WPP_SF_Sd
0x140023a00  jmp     loc_140023B57
0x140023a05  test    r13b, r13b
0x140023a08  jnz     short loc_140023A5C
0x140023a0a  mov     rcx, [rbp+hObject]; hFile
0x140023a0e  lea     r8, [rbp+var_18]; unsigned __int64
0x140023a12  mov     edx, 2; void *
0x140023a17  mov     word ptr [rbp+var_18], 0FEFFh
0x140023a1d  call    ?UtilWriteFile@CommonUtil@@YAJPEAX_KPEBX@Z; CommonUtil::UtilWriteFile(void *,unsigned __int64,void const *)
0x140023a22  mov     r14d, eax
0x140023a25  test    eax, eax
0x140023a27  jns     short loc_140023A5C
0x140023a29  mov     rcx, cs:WPP_GLOBAL_Control
0x140023a30  cmp     rcx, rdi
0x140023a33  jz      loc_140023B57
0x140023a39  test    byte ptr [rcx+1Ch], 1
0x140023a3d  jz      loc_140023B57
0x140023a43  mov     edx, 0Fh
0x140023a48  mov     rcx, [rcx+10h]
0x140023a4c  mov     r9d, r14d
0x140023a4f  mov     r8, rsi
0x140023a52  call    WPP_SF_d
0x140023a57  jmp     loc_140023B57
0x140023a5c  mov     rcx, [rbp+hObject]; this
0x140023a60  xor     r9d, r9d; unsigned int
0x140023a63  xor     edx, edx; void *
0x140023a65  lea     r8d, [r9+2]; unsigned __int64
0x140023a69  call    ?UtilSetFilePointer@CommonUtil@@YAJPEAX_KKPEA_K@Z; CommonUtil::UtilSetFilePointer(void *,unsigned __int64,ulong,unsigned __int64 *)
0x140023a6e  mov     r14d, eax
0x140023a71  test    eax, eax
0x140023a73  jns     short loc_140023A99
0x140023a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140023a7c  cmp     rcx, rdi
0x140023a7f  jz      loc_140023B57
0x140023a85  test    byte ptr [rcx+1Ch], 1
0x140023a89  jz      loc_140023B57
0x140023a8f  mov     edx, 10h
0x140023a94  jmp     loc_1400239EB
0x140023a99  mov     r8, [rbx+10h]; unsigned __int64
0x140023a9d  mov     rax, [rbx+20h]
0x140023aa1  mov     rcx, [rbp+hObject]; hFile
0x140023aa5  sub     rax, r8
0x140023aa8  sar     rax, 1
0x140023aab  lea     edx, [rax+rax]; void *
0x140023aae  call    ?UtilWriteFile@CommonUtil@@YAJPEAX_KPEBX@Z; CommonUtil::UtilWriteFile(void *,unsigned __int64,void const *)
0x140023ab3  mov     r14d, eax
0x140023ab6  test    eax, eax
0x140023ab8  jns     short loc_140023ADE
0x140023aba  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ac1  cmp     rcx, rdi
0x140023ac4  jz      loc_140023B57
0x140023aca  test    byte ptr [rcx+1Ch], 1
0x140023ace  jz      loc_140023B57
0x140023ad4  mov     edx, 11h
0x140023ad9  jmp     loc_140023A48
0x140023ade  mov     rcx, cs:WPP_GLOBAL_Control
0x140023ae5  cmp     rcx, rdi
0x140023ae8  jz      short loc_140023B10
0x140023aea  test    byte ptr [rcx+1Ch], 4
0x140023aee  jz      short loc_140023B10
0x140023af0  mov     r9, [rbx+20h]
0x140023af4  sub     r9, [rbx+10h]
0x140023af8  mov     rax, [rbx+38h]
0x140023afc  mov     rcx, [rcx+10h]; LoggerHandle
0x140023b00  sar     r9, 1
0x140023b03  add     r9d, r9d
0x140023b06  mov     [rsp+60h+var_40], rax; __int64
0x140023b0b  call    WPP_SF_DS
0x140023b10  mov     rax, [rbx+18h]
0x140023b14  mov     rcx, [rbp+hObject]; hObject
0x140023b18  mov     [rbx+28h], rax
0x140023b1c  mov     rax, [rbx+10h]
0x140023b20  mov     [rbx+20h], rax
0x140023b24  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140023b28  jz      short loc_140023B30
0x140023b2a  call    cs:__imp_CloseHandle
0x140023b30  xor     eax, eax
0x140023b32  jmp     short loc_140023B6A
0x140023b34  mov     rcx, cs:WPP_GLOBAL_Control
0x140023b3b  cmp     rcx, rdi
0x140023b3e  jz      short loc_140023B57
0x140023b40  test    byte ptr [rcx+1Ch], 1
0x140023b44  jz      short loc_140023B57
0x140023b46  mov     rcx, [rcx+10h]
0x140023b4a  mov     edx, 0Ch
0x140023b4f  mov     r8, rsi
0x140023b52  call    WPP_SF_
0x140023b57  mov     rcx, [rbp+hObject]; hObject
0x140023b5b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140023b5f  jz      short loc_140023B67
0x140023b61  call    cs:__imp_CloseHandle
0x140023b67  mov     eax, r14d
0x140023b6a  mov     rcx, [rbp+var_8]
0x140023b6e  xor     rcx, rsp; StackCookie
0x140023b71  call    __security_check_cookie
0x140023b76  lea     r11, [rsp+60h+var_s0]
0x140023b7b  mov     rbx, [r11+38h]
0x140023b7f  mov     rsi, [r11+40h]
0x140023b83  mov     rdi, [r11+48h]
0x140023b87  mov     rsp, r11
0x140023b8a  pop     r15
0x140023b8c  pop     r14
0x140023b8e  pop     r13
0x140023b90  pop     r12
0x140023b92  pop     rbp
0x140023b93  retn
```
