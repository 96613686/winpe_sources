# FwAppCFieldParserCapability(ushort const *,_tag_FW_APPCONTAINER *)

- ea: `0x180010f70`
- end: `0x18001117b`
- name: `?FwAppCFieldParserCapability@@YAJPEBGPEAU_tag_FW_APPCONTAINER@@@Z`
- size: `523`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _tag_FW_APPCONTAINER *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800042c4`
- `0x180010f70`
- `0x18001f650`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180010fb9`
- `ntdll!RtlLengthSid` at `0x180010fb9`
- `ntdll!RtlCopySid` at `0x180010fe8`
- `ntdll!RtlCopySid` at `0x180010fe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001101b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001101b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011013`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011013`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180010fa7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180010fa7`
- `fwbase!FwAlloc` at `0x180010fc4`
- `fwbase!FwAlloc` at `0x180010fc4`
- `fwbase!FwArrayAppend` at `0x180011057`
- `fwbase!FwArrayAppend` at `0x180011057`

## pseudocode

```c
__int64 __fastcall FwAppCFieldParserCapability(const unsigned __int16 *a1, struct _tag_FW_APPCONTAINER *a2)
{
  PSID v3; // r14
  ULONG v4; // r15d
  void *v5; // rax
  void *v6; // rbp
  unsigned int v7; // ebx
  LPCOLESTR v8; // rcx
  signed int LastError; // eax
  int v10; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  PSID Sid; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v15[2]; // [rsp+28h] [rbp-40h] BYREF

  v15[1] = 0;
  Sid = 0;
  v15[0] = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    v3 = Sid;
    v4 = RtlLengthSid(Sid);
    v5 = (void *)FwAlloc(v4);
    v6 = v5;
    if ( v5 )
    {
      v7 = 0;
      RtlCopySid(v4, v5, v3);
      v15[0] = v6;
    }
    else
    {
      v7 = 14;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_5;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, 14);
    }
    v8 = WPP_GLOBAL_Control;
LABEL_5:
    if ( v7 )
      v7 |= 0x80070000;
    if ( (v7 & 0x80000000) == 0 )
    {
      LocalFree(Sid);
      goto LABEL_13;
    }
    if ( v8 == (LPCOLESTR)&WPP_GLOBAL_Control )
      return v7;
    if ( (v8[14] & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v8 + 2), 51, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, v7);
      v8 = WPP_GLOBAL_Control;
    }
    goto LABEL_23;
  }
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, v7);
    v8 = WPP_GLOBAL_Control;
  }
  if ( (v7 & 0x80000000) == 0 )
  {
LABEL_13:
    v10 = FwArrayAppend(16, FwShallowCopySidAndAttributes, (char *)a2 + 64, v15);
    v7 = v10;
    if ( v10 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v12 = 57;
        v13 = (unsigned int)v10;
        goto LABEL_29;
      }
    }
    return v7;
  }
LABEL_23:
  if ( v8 != (LPCOLESTR)&WPP_GLOBAL_Control && (v8[14] & 1) != 0 )
  {
    v12 = 56;
    v13 = v7;
LABEL_29:
    WPP_SF_d(*((_QWORD *)v8 + 2), v12, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, v13);
  }
  return v7;
}

```

## disassembly

```asm
0x180010f70  mov     r11, rsp
0x180010f73  mov     [r11+18h], rbx
0x180010f77  push    rbp
0x180010f78  push    rsi
0x180010f79  push    r13
0x180010f7b  push    r14
0x180010f7d  push    r15
0x180010f7f  sub     rsp, 40h
0x180010f83  mov     rax, cs:__security_cookie
0x180010f8a  xor     rax, rsp
0x180010f8d  mov     [rsp+68h+var_30], rax
0x180010f92  xor     eax, eax
0x180010f94  mov     r13, rdx
0x180010f97  lea     rdx, [r11-48h]; Sid
0x180010f9b  mov     [r11-38h], rax
0x180010f9f  mov     [r11-48h], rax
0x180010fa3  mov     [r11-40h], rax
0x180010fa7  call    cs:__imp_ConvertStringSidToSidW
0x180010fad  test    eax, eax
0x180010faf  jz      short loc_18001101B
0x180010fb1  mov     r14, [rsp+68h+Sid]
0x180010fb6  mov     rcx, r14; Sid
0x180010fb9  call    cs:__imp_RtlLengthSid
0x180010fbf  mov     ecx, eax
0x180010fc1  mov     r15d, eax
0x180010fc4  call    cs:__imp_FwAlloc
0x180010fca  lea     rsi, WPP_GLOBAL_Control
0x180010fd1  mov     rbp, rax
0x180010fd4  test    rax, rax
0x180010fd7  jz      loc_1800110C0
0x180010fdd  xor     ebx, ebx
0x180010fdf  mov     r8, r14; SourceSid
0x180010fe2  mov     rdx, rax; DestinationSid
0x180010fe5  mov     ecx, r15d; DestinationSidLength
0x180010fe8  call    cs:__imp_RtlCopySid
0x180010fee  mov     [rsp+68h+var_40], rbp
0x180010ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ffa  mov     eax, ebx
0x180010ffc  or      eax, 80070000h
0x180011001  test    ebx, ebx
0x180011003  cmovnz  ebx, eax
0x180011006  test    ebx, ebx
0x180011008  js      loc_1800110F9
0x18001100e  mov     rcx, [rsp+68h+Sid]; hMem
0x180011013  call    cs:__imp_LocalFree
0x180011019  jmp     short loc_180011042
0x18001101b  call    cs:__imp_GetLastError
0x180011021  mov     ebx, eax
0x180011023  test    eax, eax
0x180011025  jg      short loc_18001108B
0x180011027  mov     rcx, cs:WPP_GLOBAL_Control
0x18001102e  lea     rsi, WPP_GLOBAL_Control
0x180011035  cmp     rcx, rsi
0x180011038  jnz     short loc_180011096
0x18001103a  test    ebx, ebx
0x18001103c  js      loc_180011127
0x180011042  lea     r8, [r13+40h]
0x180011046  mov     ecx, 10h
0x18001104b  lea     r9, [rsp+68h+var_40]
0x180011050  lea     rdx, ?FwShallowCopySidAndAttributes@@YAJPEBXPEAX@Z; FwShallowCopySidAndAttributes(void const *,void *)
0x180011057  call    cs:__imp_FwArrayAppend
0x18001105d  mov     ebx, eax
0x18001105f  test    eax, eax
0x180011061  js      loc_180011144
0x180011067  mov     eax, ebx
0x180011069  mov     rcx, [rsp+68h+var_30]
0x18001106e  xor     rcx, rsp; StackCookie
0x180011071  call    __security_check_cookie
0x180011076  mov     rbx, [rsp+68h+arg_10]
0x18001107e  add     rsp, 40h
0x180011082  pop     r15
0x180011084  pop     r14
0x180011086  pop     r13
0x180011088  pop     rsi
0x180011089  pop     rbp
0x18001108a  retn
0x18001108b  movzx   ebx, ax
0x18001108e  or      ebx, 80070000h
0x180011094  jmp     short loc_180011027
0x180011096  test    byte ptr [rcx+1Ch], 1
0x18001109a  jz      short loc_18001103A
0x18001109c  mov     rcx, [rcx+10h]
0x1800110a0  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x1800110a7  mov     edx, 32h ; '2'
0x1800110ac  mov     r9d, ebx
0x1800110af  call    WPP_SF_d
0x1800110b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110bb  jmp     loc_18001103A
0x1800110c0  mov     ebx, 0Eh
0x1800110c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110cc  cmp     rcx, rsi
0x1800110cf  jz      loc_180010FFA
0x1800110d5  test    byte ptr [rcx+1Ch], 1
0x1800110d9  jz      loc_180010FFA
0x1800110df  mov     rcx, [rcx+10h]
0x1800110e3  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x1800110ea  mov     edx, ebx
0x1800110ec  mov     r9d, ebx
0x1800110ef  call    WPP_SF_d
0x1800110f4  jmp     loc_180010FF3
0x1800110f9  cmp     rcx, rsi
0x1800110fc  jz      loc_180011067
0x180011102  test    byte ptr [rcx+1Ch], 1
0x180011106  jz      short loc_180011127
0x180011108  mov     rcx, [rcx+10h]
0x18001110c  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x180011113  mov     edx, 33h ; '3'
0x180011118  mov     r9d, ebx
0x18001111b  call    WPP_SF_d
0x180011120  mov     rcx, cs:WPP_GLOBAL_Control
0x180011127  cmp     rcx, rsi
0x18001112a  jz      loc_180011067
0x180011130  test    byte ptr [rcx+1Ch], 1
0x180011134  jz      loc_180011067
0x18001113a  mov     edx, 38h ; '8'
0x18001113f  mov     r9d, ebx
0x180011142  jmp     short loc_180011166
0x180011144  mov     rcx, cs:WPP_GLOBAL_Control
0x18001114b  cmp     rcx, rsi
0x18001114e  jz      loc_180011067
0x180011154  test    byte ptr [rcx+1Ch], 1
0x180011158  jz      loc_180011067
0x18001115e  mov     edx, 39h ; '9'
0x180011163  mov     r9d, eax
0x180011166  mov     rcx, [rcx+10h]
0x18001116a  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x180011171  call    WPP_SF_d
0x180011176  jmp     loc_180011067
```
