# UtilAddUserReadAccessToSample

- ea: `0x1800057f4`
- end: `0x18000593d`
- name: `UtilAddUserReadAccessToSample`
- size: `329`
- prototype: `__int64 __fastcall(wchar_t *Str, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005010`

## callees

- `0x180004b7c`
- `0x1800057f4`
- `0x18000649c`
- `0x180006a2c`
- `0x180007148`
- `0x180007a44`

## import_xrefs

- `msvcrt!wcschr` at `0x18000580e`
- `msvcrt!wcschr` at `0x180005823`
- `msvcrt!wcschr` at `0x18000580e`
- `msvcrt!wcschr` at `0x180005823`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000588b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800058ad`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800058df`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000588b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800058ad`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800058df`
- `mpclient!MpFreeMemory` at `0x180005852`
- `mpclient!MpFreeMemory` at `0x1800058bc`
- `mpclient!MpFreeMemory` at `0x1800058ee`
- `mpclient!MpFreeMemory` at `0x180005852`
- `mpclient!MpFreeMemory` at `0x1800058bc`
- `mpclient!MpFreeMemory` at `0x1800058ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UtilAddUserReadAccessToSample(wchar_t *Str, __int64 a2)
{
  unsigned __int16 **v4; // rdx
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r9
  int ConfigStringValue; // ebx
  const unsigned __int16 *v8; // rdx
  CommonUtil *v9; // rbx
  int IsFileExists; // edi
  enum tagMP_CONFIG_ORIGIN *savedregs; // [rsp+20h] [rbp+0h]
  unsigned __int16 *v13; // [rsp+50h] [rbp+30h] BYREF
  CommonUtil *v14; // [rsp+58h] [rbp+38h] BYREF

  if ( wcschr(Str, 0x5Cu) || wcschr(Str, 0x2Fu) )
  {
    ConfigStringValue = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_85f567f30ac03a1b1e78961f0afc6072_Traceguids, 2147942487LL);
    return (unsigned int)ConfigStringValue;
  }
  v13 = 0;
  ConfigStringValue = MpConfigUtils::GetConfigStringValue((MpConfigUtils *)&v13, v4, v5, v6, savedregs);
  if ( ConfigStringValue < 0 )
  {
LABEL_4:
    if ( v13 )
      MpFreeMemory();
    return (unsigned int)ConfigStringValue;
  }
  v14 = 0;
  ConfigStringValue = CommonUtil::NewSprintfW((CommonUtil *)&v14, (unsigned __int16 **)L"%s\\%s", v13, Str);
  if ( ConfigStringValue < 0 )
  {
    if ( v14 )
      operator delete[](v14);
    goto LABEL_4;
  }
  v9 = v14;
  IsFileExists = CommonUtil::UtilIsFileExists(v14, v8);
  if ( IsFileExists < 0 || (IsFileExists = CommonUtil::HrSetFileAccess(v9, a2), IsFileExists < 0) )
  {
    if ( v9 )
      operator delete[](v9);
    if ( v13 )
      MpFreeMemory();
    return (unsigned int)IsFileExists;
  }
  else
  {
    if ( v9 )
      operator delete[](v9);
    if ( v13 )
      MpFreeMemory();
    return 0;
  }
}

```

## disassembly

```asm
0x1800057f4  mov     [rsp-18h+arg_0], rbx
0x1800057f9  push    rbp
0x1800057fa  push    rsi
0x1800057fb  push    rdi; enum tagMP_CONFIG_ORIGIN *
0x1800057fc  mov     rbp, rsp
0x1800057ff  sub     rsp, 20h
0x180005803  mov     rsi, rdx
0x180005806  mov     rdi, rcx
0x180005809  mov     edx, 5Ch ; '\'; Ch
0x18000580e  call    cs:__imp_wcschr
0x180005814  test    rax, rax
0x180005817  jnz     loc_1800058F8
0x18000581d  lea     edx, [rax+2Fh]; Ch
0x180005820  mov     rcx, rdi; Str
0x180005823  call    cs:__imp_wcschr
0x180005829  test    rax, rax
0x18000582c  jnz     loc_1800058F8
0x180005832  lea     rcx, [rbp+arg_10]; this
0x180005836  mov     [rbp+arg_10], rax
0x18000583a  call    ?GetConfigStringValue@MpConfigUtils@@YAJPEAPEAGPEBG1PEAW4tagMP_CONFIG_ORIGIN@@@Z; MpConfigUtils::GetConfigStringValue(ushort * *,ushort const *,ushort const *,tagMP_CONFIG_ORIGIN *)
0x18000583f  mov     ebx, eax
0x180005841  test    eax, eax
0x180005843  jns     short loc_18000585D
0x180005845  mov     rcx, [rbp+arg_10]
0x180005849  test    rcx, rcx
0x18000584c  jz      loc_18000592E
0x180005852  call    cs:__imp_MpFreeMemory
0x180005858  jmp     loc_18000592E
0x18000585d  mov     r8, [rbp+arg_10]; unsigned __int16 *
0x180005861  lea     rdx, aSS; "%s\\%s"
0x180005868  mov     r9, rdi
0x18000586b  mov     [rbp+arg_18], 0
0x180005873  lea     rcx, [rbp+arg_18]; this
0x180005877  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x18000587c  mov     ebx, eax
0x18000587e  test    eax, eax
0x180005880  jns     short loc_180005893
0x180005882  mov     rcx, [rbp+arg_18]
0x180005886  test    rcx, rcx
0x180005889  jz      short loc_180005845
0x18000588b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180005891  jmp     short loc_180005845
0x180005893  mov     rbx, [rbp+arg_18]
0x180005897  mov     rcx, rbx; this
0x18000589a  call    ?UtilIsFileExists@CommonUtil@@YAJPEBG@Z; CommonUtil::UtilIsFileExists(ushort const *)
0x18000589f  mov     edi, eax
0x1800058a1  test    eax, eax
0x1800058a3  jns     short loc_1800058C6
0x1800058a5  test    rbx, rbx
0x1800058a8  jz      short loc_1800058B3
0x1800058aa  mov     rcx, rbx
0x1800058ad  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800058b3  mov     rcx, [rbp+arg_10]
0x1800058b7  test    rcx, rcx
0x1800058ba  jz      short loc_1800058C2
0x1800058bc  call    cs:__imp_MpFreeMemory
0x1800058c2  mov     eax, edi
0x1800058c4  jmp     short loc_180005930
0x1800058c6  mov     rdx, rsi
0x1800058c9  mov     rcx, rbx
0x1800058cc  call    ?HrSetFileAccess@CommonUtil@@YAJPEBGPEAXKW4ACCESS_ACL_TYPE@1@@Z; CommonUtil::HrSetFileAccess(ushort const *,void *,ulong,CommonUtil::ACCESS_ACL_TYPE)
0x1800058d1  mov     edi, eax
0x1800058d3  test    eax, eax
0x1800058d5  js      short loc_1800058A5
0x1800058d7  test    rbx, rbx
0x1800058da  jz      short loc_1800058E5
0x1800058dc  mov     rcx, rbx
0x1800058df  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800058e5  mov     rcx, [rbp+arg_10]
0x1800058e9  test    rcx, rcx
0x1800058ec  jz      short loc_1800058F4
0x1800058ee  call    cs:__imp_MpFreeMemory
0x1800058f4  xor     eax, eax
0x1800058f6  jmp     short loc_180005930
0x1800058f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058ff  lea     rdx, WPP_GLOBAL_Control
0x180005906  mov     ebx, 80070057h
0x18000590b  cmp     rcx, rdx
0x18000590e  jz      short loc_18000592E
0x180005910  test    byte ptr [rcx+1Ch], 1
0x180005914  jz      short loc_18000592E
0x180005916  mov     rcx, [rcx+10h]
0x18000591a  lea     r8, WPP_85f567f30ac03a1b1e78961f0afc6072_Traceguids
0x180005921  mov     edx, 17h
0x180005926  mov     r9d, ebx
0x180005929  call    WPP_SF_d
0x18000592e  mov     eax, ebx
0x180005930  mov     rbx, [rsp+20h+arg_0]
0x180005935  add     rsp, 20h
0x180005939  pop     rdi
0x18000593a  pop     rsi
0x18000593b  pop     rbp
0x18000593c  retn
```
