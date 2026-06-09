# ShieldProvider::LoadSystemPathFromFileHandle

- ea: `0x140004e84`
- end: `0x1400050bd`
- name: `ShieldProvider::LoadSystemPathFromFileHandle`
- size: `569`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140005110`

## callees

- `0x1400015f4`
- `0x140003640`
- `0x140004e84`
- `0x140005e1c`
- `0x14000e990`
- `0x14000eb7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140005005`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140005005`
- `KERNEL32!GetSystemDirectoryW` at `0x140004e93`
- `KERNEL32!CloseHandle` at `0x140004f5f`
- `KERNEL32!CloseHandle` at `0x140004fdf`
- `KERNEL32!CloseHandle` at `0x14000505b`
- `KERNEL32!CloseHandle` at `0x14000509b`
- `KERNEL32!CloseHandle` at `0x140004f5f`
- `KERNEL32!CloseHandle` at `0x140004fdf`
- `KERNEL32!CloseHandle` at `0x14000505b`
- `KERNEL32!CloseHandle` at `0x14000509b`

## string_xrefs

- `0x140004e9a`: `ntdll.dll`

## pseudocode

```c
__int64 ShieldProvider::LoadSystemPathFromFileHandle()
{
  int WindowsPath; // eax
  const unsigned __int16 *v1; // r8
  __int64 v2; // r9
  unsigned int v3; // ebx
  _UNKNOWN **v4; // rdx
  wchar_t *v6; // rbx
  int File; // eax
  void *v8; // r8
  unsigned int v9; // r9d
  unsigned int v10; // edi
  _UNKNOWN **v11; // rdx
  HANDLE v12; // rdi
  int FileNameFromFileHandle; // eax
  unsigned int v14; // esi
  _UNKNOWN **v15; // rdx
  wchar_t *v16; // rsi
  wchar_t *v17; // rax
  unsigned __int64 v18; // rdx
  _UNKNOWN **v19; // rdx
  unsigned int v20; // [rsp+20h] [rbp-20h]
  wchar_t *Str; // [rsp+60h] [rbp+20h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp+28h] BYREF

  Str = 0;
  WindowsPath = CommonUtil::UtilGetWindowsPath(GetSystemDirectoryW, &Str, L"ntdll.dll");
  v3 = WindowsPath;
  if ( WindowsPath >= 0 )
  {
    v6 = Str;
    hObject = (HANDLE)-1LL;
    File = CommonUtil::UtilCreateFile((CommonUtil *)&hObject, Str, v1, v2, v20, 0);
    v10 = File;
    if ( File >= 0 )
    {
      v12 = hObject;
      Str = 0;
      FileNameFromFileHandle = ShieldProvider::GetFileNameFromFileHandle(
                                 (ShieldProvider *)&Str,
                                 (unsigned __int16 **)hObject,
                                 v8,
                                 v9);
      v14 = FileNameFromFileHandle;
      if ( FileNameFromFileHandle >= 0 )
      {
        v16 = Str;
        v17 = wcsrchr(Str, 0x5Cu);
        if ( v17 )
        {
          *v17 = 0;
          if ( String1 )
            operator delete(String1, v18);
          String1 = v16;
          if ( v12 != (HANDLE)-1LL )
            CloseHandle(v12);
          if ( v6 )
            operator delete(v6, v18);
          return 0;
        }
        else
        {
          v19 = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              20,
              WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
              2147942523LL);
          if ( v16 )
            operator delete(v16, (unsigned __int64)v19);
          if ( v12 != (HANDLE)-1LL )
            CloseHandle(v12);
          if ( v6 )
            operator delete(v6, (unsigned __int64)v19);
          return 2147942523LL;
        }
      }
      else
      {
        v15 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
            (unsigned int)FileNameFromFileHandle);
        if ( Str )
          operator delete(Str, (unsigned __int64)v15);
        if ( v12 != (HANDLE)-1LL )
          CloseHandle(v12);
        if ( v6 )
          operator delete(v6, (unsigned __int64)v15);
        return v14;
      }
    }
    else
    {
      v11 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
          (unsigned int)File);
      if ( hObject != (HANDLE)-1LL )
        CloseHandle(hObject);
      if ( v6 )
        operator delete(v6, (unsigned __int64)v11);
      return v10;
    }
  }
  else
  {
    v4 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
        (unsigned int)WindowsPath);
    if ( Str )
      operator delete(Str, (unsigned __int64)v4);
    return v3;
  }
}

```

## disassembly

```asm
0x140004e84  mov     [rsp-18h+arg_10], rbx
0x140004e89  push    rbp
0x140004e8a  push    rsi
0x140004e8b  push    rdi; void *
0x140004e8c  mov     rbp, rsp
0x140004e8f  sub     rsp, 40h
0x140004e93  mov     rcx, cs:__imp_GetSystemDirectoryW
0x140004e9a  lea     r8, aNtdllDll_0; "ntdll.dll"
0x140004ea1  lea     rdx, [rbp+Str]
0x140004ea5  mov     [rbp+Str], 0
0x140004ead  call    CommonUtil__UtilGetWindowsPath
0x140004eb2  mov     ebx, eax
0x140004eb4  test    eax, eax
0x140004eb6  jns     short loc_140004EFE
0x140004eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ebf  lea     rdx, WPP_GLOBAL_Control
0x140004ec6  cmp     rcx, rdx
0x140004ec9  jz      short loc_140004EE9
0x140004ecb  test    byte ptr [rcx+1Ch], 1
0x140004ecf  jz      short loc_140004EE9
0x140004ed1  mov     rcx, [rcx+10h]
0x140004ed5  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x140004edc  mov     edx, 11h
0x140004ee1  mov     r9d, eax
0x140004ee4  call    WPP_SF_d
0x140004ee9  mov     rcx, [rbp+Str]; void *
0x140004eed  test    rcx, rcx
0x140004ef0  jz      short loc_140004EF7
0x140004ef2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004ef7  mov     eax, ebx
0x140004ef9  jmp     loc_1400050B0
0x140004efe  mov     rbx, [rbp+Str]
0x140004f02  lea     rcx, [rbp+hObject]; this
0x140004f06  mov     rdx, rbx; void **
0x140004f09  mov     [rbp+hObject], 0FFFFFFFFFFFFFFFFh
0x140004f11  mov     [rsp+40h+var_18], 0; unsigned int
0x140004f19  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEBGKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,ushort const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x140004f1e  mov     edi, eax
0x140004f20  test    eax, eax
0x140004f22  jns     short loc_140004F79
0x140004f24  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f2b  lea     rdx, WPP_GLOBAL_Control
0x140004f32  cmp     rcx, rdx
0x140004f35  jz      short loc_140004F55
0x140004f37  test    byte ptr [rcx+1Ch], 1
0x140004f3b  jz      short loc_140004F55
0x140004f3d  mov     rcx, [rcx+10h]
0x140004f41  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x140004f48  mov     edx, 12h
0x140004f4d  mov     r9d, eax
0x140004f50  call    WPP_SF_d
0x140004f55  mov     rcx, [rbp+hObject]; hObject
0x140004f59  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140004f5d  jz      short loc_140004F65
0x140004f5f  call    cs:__imp_CloseHandle
0x140004f65  test    rbx, rbx
0x140004f68  jz      short loc_140004F72
0x140004f6a  mov     rcx, rbx; void *
0x140004f6d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004f72  mov     eax, edi
0x140004f74  jmp     loc_1400050B0
0x140004f79  mov     rdi, [rbp+hObject]
0x140004f7d  lea     rcx, [rbp+Str]; this
0x140004f81  mov     rdx, rdi; unsigned __int16 **
0x140004f84  mov     [rbp+Str], 0
0x140004f8c  call    ?GetFileNameFromFileHandle@ShieldProvider@@YAJPEAPEAGPEAXK@Z; ShieldProvider::GetFileNameFromFileHandle(ushort * *,void *,ulong)
0x140004f91  mov     esi, eax
0x140004f93  test    eax, eax
0x140004f95  jns     short loc_140004FF9
0x140004f97  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f9e  lea     rdx, WPP_GLOBAL_Control
0x140004fa5  cmp     rcx, rdx
0x140004fa8  jz      short loc_140004FC8
0x140004faa  test    byte ptr [rcx+1Ch], 1
0x140004fae  jz      short loc_140004FC8
0x140004fb0  mov     rcx, [rcx+10h]
0x140004fb4  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x140004fbb  mov     edx, 13h
0x140004fc0  mov     r9d, eax
0x140004fc3  call    WPP_SF_d
0x140004fc8  mov     rcx, [rbp+Str]; void *
0x140004fcc  test    rcx, rcx
0x140004fcf  jz      short loc_140004FD6
0x140004fd1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004fd6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140004fda  jz      short loc_140004FE5
0x140004fdc  mov     rcx, rdi; hObject
0x140004fdf  call    cs:__imp_CloseHandle
0x140004fe5  test    rbx, rbx
0x140004fe8  jz      short loc_140004FF2
0x140004fea  mov     rcx, rbx; void *
0x140004fed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004ff2  mov     eax, esi
0x140004ff4  jmp     loc_1400050B0
0x140004ff9  mov     rsi, [rbp+Str]
0x140004ffd  mov     edx, 5Ch ; '\'; Ch
0x140005002  mov     rcx, rsi; Str
0x140005005  call    cs:__imp_wcsrchr
0x14000500b  mov     rcx, rax
0x14000500e  test    rax, rax
0x140005011  jnz     short loc_140005075
0x140005013  mov     rcx, cs:WPP_GLOBAL_Control
0x14000501a  lea     rdx, WPP_GLOBAL_Control
0x140005021  cmp     rcx, rdx
0x140005024  jz      short loc_140005045
0x140005026  test    byte ptr [rcx+1Ch], 1
0x14000502a  jz      short loc_140005045
0x14000502c  mov     rcx, [rcx+10h]
0x140005030  lea     edx, [rax+14h]
0x140005033  mov     r9d, 8007007Bh
0x140005039  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x140005040  call    WPP_SF_d
0x140005045  test    rsi, rsi
0x140005048  jz      short loc_140005052
0x14000504a  mov     rcx, rsi; void *
0x14000504d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005052  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140005056  jz      short loc_140005061
0x140005058  mov     rcx, rdi; hObject
0x14000505b  call    cs:__imp_CloseHandle
0x140005061  test    rbx, rbx
0x140005064  jz      short loc_14000506E
0x140005066  mov     rcx, rbx; void *
0x140005069  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000506e  mov     eax, 8007007Bh
0x140005073  jmp     short loc_1400050B0
0x140005075  xor     eax, eax
0x140005077  mov     [rcx], ax
0x14000507a  mov     rcx, cs:String1; void *
0x140005081  test    rcx, rcx
0x140005084  jz      short loc_14000508B
0x140005086  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000508b  mov     cs:String1, rsi
0x140005092  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140005096  jz      short loc_1400050A1
0x140005098  mov     rcx, rdi; hObject
0x14000509b  call    cs:__imp_CloseHandle
0x1400050a1  test    rbx, rbx
0x1400050a4  jz      short loc_1400050AE
0x1400050a6  mov     rcx, rbx; void *
0x1400050a9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400050ae  xor     eax, eax
0x1400050b0  mov     rbx, [rsp+40h+arg_10]
0x1400050b5  add     rsp, 40h
0x1400050b9  pop     rdi
0x1400050ba  pop     rsi
0x1400050bb  pop     rbp
0x1400050bc  retn
```
