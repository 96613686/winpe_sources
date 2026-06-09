# GetMrcDir(ushort *,unsigned __int64 *)

- ea: `0x1800047c4`
- end: `0x180004903`
- name: `?GetMrcDir@@YAKPEAGPEA_K@Z`
- size: `319`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003b58`
- `0x180004714`

## callees

- `0x180002eb8`
- `0x1800047c4`
- `0x180004c44`
- `0x180004dec`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800048a3`
- `KERNEL32!GetLastError` at `0x1800048a3`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180004829`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180004829`

## string_xrefs

- `0x180004822`: `%PROGRAMDATA%`
- `0x180004885`: `Microsoft\Windows\DeviceMetadataCache`

## pseudocode

```c
__int64 __fastcall GetMrcDir(unsigned __int16 *a1, unsigned __int64 *a2)
{
  bool v2; // zf
  DWORD LastError; // ebx
  DWORD v6; // ecx
  unsigned __int64 v7; // rsi
  int v8; // eax
  WCHAR Dst[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = *a2 == 0;
  if ( !*a2 )
  {
    if ( a1 )
      return 87;
    v2 = *a2 == 0;
  }
  if ( v2 )
  {
    if ( !a1 )
      goto LABEL_9;
  }
  else if ( !a1 )
  {
    return 87;
  }
  *a1 = 0;
LABEL_9:
  v6 = ExpandEnvironmentStringsW(L"%PROGRAMDATA%", Dst, 0x104u);
  if ( v6 - 1 > 0x103 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_bab4a60a0f10308a353b12310872734a_Traceguids, LastError);
  }
  else
  {
    v7 = v6 + 1 + 39LL;
    if ( v7 <= *a2 )
    {
      v8 = StringCchCopyW(a1, *a2, Dst);
      if ( v8 < 0 )
        return (unsigned __int16)v8;
      v8 = StringCchCatW(a1, *a2, L"\\");
      if ( v8 < 0 )
        return (unsigned __int16)v8;
      v8 = StringCchCatW(a1, *a2, L"Microsoft\\Windows\\DeviceMetadataCache");
      if ( v8 < 0 )
      {
        return (unsigned __int16)v8;
      }
      else
      {
        LastError = 0;
        *a2 = v7 - 1;
      }
    }
    else
    {
      *a2 = v7;
      return 122;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800047c4  mov     [rsp+arg_10], rbx
0x1800047c9  mov     [rsp+arg_18], rsi
0x1800047ce  push    rdi
0x1800047cf  sub     rsp, 240h
0x1800047d6  mov     rax, cs:__security_cookie
0x1800047dd  xor     rax, rsp
0x1800047e0  mov     [rsp+248h+var_18], rax
0x1800047e8  cmp     qword ptr [rdx], 0
0x1800047ec  mov     rdi, rdx
0x1800047ef  mov     rbx, rcx
0x1800047f2  jnz     short loc_1800047FC
0x1800047f4  test    rcx, rcx
0x1800047f7  jnz     short loc_180004803
0x1800047f9  cmp     [rdx], rcx
0x1800047fc  jbe     short loc_18000480D
0x1800047fe  test    rbx, rbx
0x180004801  jnz     short loc_180004812
0x180004803  mov     ebx, 57h ; 'W'
0x180004808  jmp     loc_1800048DC
0x18000480d  test    rbx, rbx
0x180004810  jz      short loc_180004817
0x180004812  xor     eax, eax
0x180004814  mov     [rcx], ax
0x180004817  mov     r8d, 104h; nSize
0x18000481d  lea     rdx, [rsp+248h+Dst]; lpDst
0x180004822  lea     rcx, Src; "%PROGRAMDATA%"
0x180004829  call    cs:__imp_ExpandEnvironmentStringsW
0x18000482f  mov     ecx, eax
0x180004831  dec     eax
0x180004833  cmp     eax, 103h
0x180004838  ja      short loc_1800048A3
0x18000483a  lea     esi, [rcx+1]
0x18000483d  add     rsi, 27h ; '''
0x180004841  cmp     rsi, [rdi]
0x180004844  jbe     short loc_180004853
0x180004846  mov     [rdi], rsi
0x180004849  mov     ebx, 7Ah ; 'z'
0x18000484e  jmp     loc_1800048DC
0x180004853  mov     rdx, [rdi]; unsigned __int64
0x180004856  lea     r8, [rsp+248h+Dst]; unsigned __int16 *
0x18000485b  mov     rcx, rbx; unsigned __int16 *
0x18000485e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004863  test    eax, eax
0x180004865  jns     short loc_18000486C
0x180004867  movzx   ebx, ax
0x18000486a  jmp     short loc_1800048DC
0x18000486c  mov     rdx, [rdi]; unsigned __int64
0x18000486f  lea     r8, asc_180016E08; "\\"
0x180004876  mov     rcx, rbx; unsigned __int16 *
0x180004879  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000487e  test    eax, eax
0x180004880  js      short loc_180004867
0x180004882  mov     rdx, [rdi]; unsigned __int64
0x180004885  lea     r8, aMicrosoftWindo; "Microsoft\\Windows\\DeviceMetadataCache"
0x18000488c  mov     rcx, rbx; unsigned __int16 *
0x18000488f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004894  test    eax, eax
0x180004896  js      short loc_180004867
0x180004898  lea     rax, [rsi-1]
0x18000489c  xor     ebx, ebx
0x18000489e  mov     [rdi], rax
0x1800048a1  jmp     short loc_1800048DC
0x1800048a3  call    cs:__imp_GetLastError
0x1800048a9  mov     ebx, eax
0x1800048ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048b2  lea     rax, WPP_GLOBAL_Control
0x1800048b9  cmp     rcx, rax
0x1800048bc  jz      short loc_1800048DC
0x1800048be  test    byte ptr [rcx+1Ch], 1
0x1800048c2  jz      short loc_1800048DC
0x1800048c4  mov     rcx, [rcx+10h]
0x1800048c8  lea     r8, WPP_bab4a60a0f10308a353b12310872734a_Traceguids
0x1800048cf  mov     edx, 0Ch
0x1800048d4  mov     r9d, ebx
0x1800048d7  call    WPP_SF_d
0x1800048dc  mov     eax, ebx
0x1800048de  mov     rcx, [rsp+248h+var_18]
0x1800048e6  xor     rcx, rsp; StackCookie
0x1800048e9  call    __security_check_cookie
0x1800048ee  lea     r11, [rsp+248h+var_8]
0x1800048f6  mov     rbx, [r11+20h]
0x1800048fa  mov     rsi, [r11+28h]
0x1800048fe  mov     rsp, r11
0x180004901  pop     rdi
0x180004902  retn
```
