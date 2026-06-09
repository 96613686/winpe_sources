# WdcStartupMonitor::LoadRegistryList(ushort const *,HKEY__ *,unsigned __int64,HKEY__ *)

- ea: `0x1800d5540`
- end: `0x1800d57e1`
- name: `?LoadRegistryList@WdcStartupMonitor@@QEAAJPEBGPEAUHKEY__@@_K1@Z`
- size: `673`
- prototype: `__int64 __usercall@<rax>(WdcStartupMonitor *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, HKEY@<r8>, unsigned __int64@<r9>, HKEY)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800d57e8`

## callees

- `0x1800d0ff8`
- `0x1800d10fc`
- `0x1800d294c`
- `0x1800d5540`
- `0x1800d5988`
- `0x1800d631c`
- `0x1800d6d44`
- `0x1800d6ea4`
- `0x1800d728c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d55fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5626`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d56c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d579b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d57a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d57b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d55fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5626`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d56c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d579b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d57a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d57b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d56d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d56e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d56d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d56e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d55d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d55d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WdcStartupMonitor::LoadRegistryList(
        WdcStartupMonitor *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int64 a4,
        HKEY hKey)
{
  DWORD v7; // r14d
  HSTRING v8; // rbx
  struct StartupDB::StartupApproval *StartupApprovalObject; // rsi
  LSTATUS v10; // eax
  unsigned int v11; // edi
  unsigned int v12; // edi
  int v13; // r8d
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v15; // rax
  const OLECHAR *v16; // rbx
  const unsigned __int16 *v17; // rax
  __int64 v18; // rdx
  struct _WDC_STARTUP_INFO *v19; // rsi
  WdcStartupMonitor *v20; // rcx
  bool v21; // r8
  bool v23[4]; // [rsp+68h] [rbp-21h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-1Dh] BYREF
  unsigned int v25; // [rsp+70h] [rbp-19h]
  HSTRING v26; // [rsp+78h] [rbp-11h] BYREF
  HSTRING string; // [rsp+80h] [rbp-9h] BYREF
  unsigned int v28; // [rsp+88h] [rbp-1h] BYREF
  HSTRING v29; // [rsp+90h] [rbp+7h] BYREF
  struct _WDC_STARTUP_INFO *v30; // [rsp+98h] [rbp+Fh] BYREF
  struct _FILETIME v31; // [rsp+A0h] [rbp+17h] BYREF
  struct StartupDB::StartupApproval *v32; // [rsp+A8h] [rbp+1Fh]

  v7 = 0;
  string = 0;
  v26 = 0;
  v8 = 0;
  v29 = 0;
  cValues = 0;
  v28 = 0;
  v23[0] = 0;
  v31 = 0;
  StartupApprovalObject = WdcStartupMonitor::_GetStartupApprovalObject(this, a4);
  v32 = StartupApprovalObject;
  v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v11 = 0;
  v25 = 0;
  if ( v10 )
  {
    if ( v10 > 0 )
      v12 = (unsigned __int16)v10 | 0x80070000;
    else
      v12 = v10;
    v25 = v12;
    WindowsDeleteString(0);
    v11 = 0;
  }
  else
  {
    if ( cValues )
    {
      do
      {
        v30 = 0;
        WindowsDeleteString(string);
        string = 0;
        if ( TmRegKeyEnum(hKey, v7, v13, &string) >= 0 )
        {
          WindowsDeleteString(v26);
          v26 = 0;
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( (int)TmRegGetSZAndExpSZValue(hKey, StringRawBuffer, &v26) >= 0 )
          {
            if ( v26 )
            {
              v15 = WindowsGetStringRawBuffer(string, 0);
              if ( WdcStartupMonitor::_GetApprovalItemStatus(
                     (WdcStartupMonitor *)v23,
                     StartupApprovalObject,
                     v15,
                     (enum _tagTM_ITEMSTATUS *)&v28,
                     v23,
                     &v31) >= 0 )
              {
                WindowsDeleteString(v8);
                v29 = 0;
                v16 = WindowsGetStringRawBuffer(string, 0);
                v17 = WindowsGetStringRawBuffer(v26, 0);
                if ( (int)WdcStartupMonitor::SetData(
                            this,
                            v17,
                            v16,
                            a2,
                            &v31,
                            v28,
                            v23[0],
                            0,
                            a3,
                            0,
                            (HSTRING)&v29,
                            (HSTRING *)&v30) < 0 )
                {
                  v8 = v29;
                }
                else
                {
                  WdcStartupMonitor::MapStartupProcesses(this, v18, &v30);
                  v19 = v30;
                  *((_BYTE *)v30 + 577) = 0;
                  *((_QWORD *)v19 + 4) = a4;
                  v8 = v29;
                  WdcStartupMonitor::_SetIcon(v20, v29, v21, v19);
                  if ( *((_BYTE *)v19 + 578) )
                    WdcStartupMonitor::DisableItem(this, v19);
                  StartupApprovalObject = v32;
                }
              }
            }
          }
        }
        ++v7;
      }
      while ( v7 < cValues );
      v11 = v25;
    }
    WindowsDeleteString(v8);
  }
  WindowsDeleteString(v26);
  v26 = 0;
  WindowsDeleteString(string);
  return v11;
}

```

## disassembly

```asm
0x1800d5540  mov     rax, rsp
0x1800d5543  mov     [rax+8], rbx
0x1800d5547  mov     [rax+20h], rsi
0x1800d554b  mov     [rax+18h], r8
0x1800d554f  mov     [rax+10h], rdx
0x1800d5553  push    rbp
0x1800d5554  push    rdi
0x1800d5555  push    r13
0x1800d5557  push    r14
0x1800d5559  push    r15
0x1800d555b  lea     rbp, [rax-57h]
0x1800d555f  sub     rsp, 0B0h
0x1800d5566  mov     r13, r9
0x1800d5569  mov     r15, rcx
0x1800d556c  xor     r14d, r14d
0x1800d556f  mov     [rbp+4Fh+string], r14
0x1800d5573  mov     [rbp+4Fh+var_60], r14
0x1800d5577  mov     ebx, r14d
0x1800d557a  mov     [rbp+4Fh+var_48], rbx
0x1800d557e  mov     [rbp+4Fh+cValues], r14d
0x1800d5582  mov     [rbp+4Fh+var_50], r14d
0x1800d5586  mov     [rbp+4Fh+var_70], r14b
0x1800d558a  mov     qword ptr [rbp+4Fh+var_38.dwLowDateTime], r14
0x1800d558e  mov     rdx, r9; unsigned __int64
0x1800d5591  call    ?_GetStartupApprovalObject@WdcStartupMonitor@@AEAAPEAVStartupApproval@StartupDB@@_K@Z; WdcStartupMonitor::_GetStartupApprovalObject(unsigned __int64)
0x1800d5596  mov     rsi, rax
0x1800d5599  mov     [rbp+4Fh+var_30], rax
0x1800d559d  mov     [rsp+0D0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800d55a2  mov     [rsp+0D0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800d55a7  mov     [rsp+0D0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800d55ac  mov     [rsp+0D0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800d55b1  lea     rax, [rbp+4Fh+cValues]
0x1800d55b5  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x1800d55ba  mov     [rsp+0D0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800d55bf  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800d55c4  mov     [rsp+0D0h+lpcSubKeys], r14; lpcSubKeys
0x1800d55c9  xor     r9d, r9d; lpReserved
0x1800d55cc  xor     r8d, r8d; lpcchClass
0x1800d55cf  xor     edx, edx; lpClass
0x1800d55d1  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800d55d5  call    cs:__imp_RegQueryInfoKeyW
0x1800d55db  mov     edi, r14d
0x1800d55de  mov     [rbp+4Fh+var_68], r14d
0x1800d55e2  test    eax, eax
0x1800d55e4  jz      short loc_1800D560C
0x1800d55e6  jg      short loc_1800D55EC
0x1800d55e8  mov     edi, eax
0x1800d55ea  jmp     short loc_1800D55F5
0x1800d55ec  movzx   edi, ax
0x1800d55ef  or      edi, 80070000h
0x1800d55f5  mov     [rbp+4Fh+var_68], edi
0x1800d55f8  test    edi, edi
0x1800d55fa  jns     short loc_1800D560C
0x1800d55fc  xor     ecx, ecx; string
0x1800d55fe  call    cs:__imp_WindowsDeleteString
0x1800d5604  mov     edi, r14d
0x1800d5607  jmp     loc_1800D57A4
0x1800d560c  cmp     [rbp+4Fh+cValues], 0
0x1800d5610  jbe     loc_1800D5798
0x1800d5616  mov     rdi, [rbp+4Fh+arg_10]
0x1800d561a  mov     [rbp+4Fh+var_40], 0
0x1800d5622  mov     rcx, [rbp+4Fh+string]; string
0x1800d5626  call    cs:__imp_WindowsDeleteString
0x1800d562c  mov     [rbp+4Fh+string], 0
0x1800d5634  lea     r9, [rbp+4Fh+string]; HSTRING *
0x1800d5638  mov     edx, r14d; unsigned int
0x1800d563b  mov     rcx, [rbp+4Fh+hKey]; HKEY
0x1800d563f  call    ?TmRegKeyEnum@@YAJPEAUHKEY__@@KHPEAPEAUHSTRING__@@@Z; TmRegKeyEnum(HKEY__ *,ulong,int,HSTRING__ * *)
0x1800d5644  test    eax, eax
0x1800d5646  js      loc_1800D5788
0x1800d564c  mov     rcx, [rbp+4Fh+var_60]; string
0x1800d5650  call    cs:__imp_WindowsDeleteString
0x1800d5656  mov     [rbp+4Fh+var_60], 0
0x1800d565e  xor     edx, edx; length
0x1800d5660  mov     rcx, [rbp+4Fh+string]; string
0x1800d5664  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d566a  lea     r8, [rbp+4Fh+var_60]; string
0x1800d566e  mov     rdx, rax; lpValueName
0x1800d5671  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800d5675  call    ?TmRegGetSZAndExpSZValue@@YAJPEAUHKEY__@@PEBGPEAPEAUHSTRING__@@@Z; TmRegGetSZAndExpSZValue(HKEY__ *,ushort const *,HSTRING__ * *)
0x1800d567a  test    eax, eax
0x1800d567c  js      loc_1800D5788
0x1800d5682  cmp     [rbp+4Fh+var_60], 0
0x1800d5687  jz      loc_1800D5788
0x1800d568d  xor     edx, edx; length
0x1800d568f  mov     rcx, [rbp+4Fh+string]; string
0x1800d5693  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d5699  lea     rcx, [rbp+4Fh+var_38]
0x1800d569d  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rcx; struct _FILETIME *
0x1800d56a2  lea     rcx, [rbp+4Fh+var_70]; this
0x1800d56a6  mov     [rsp+0D0h+lpcSubKeys], rcx; bool *
0x1800d56ab  lea     r9, [rbp+4Fh+var_50]; enum _tagTM_ITEMSTATUS *
0x1800d56af  mov     r8, rax; unsigned __int16 *
0x1800d56b2  mov     rdx, rsi; struct StartupDB::StartupApproval *
0x1800d56b5  call    ?_GetApprovalItemStatus@WdcStartupMonitor@@AEAAJPEAVStartupApproval@StartupDB@@PEBGPEAW4_tagTM_ITEMSTATUS@@PEA_NPEAU_FILETIME@@@Z; WdcStartupMonitor::_GetApprovalItemStatus(StartupDB::StartupApproval *,ushort const *,_tagTM_ITEMSTATUS *,bool *,_FILETIME *)
0x1800d56ba  test    eax, eax
0x1800d56bc  js      loc_1800D5788
0x1800d56c2  mov     rcx, rbx; string
0x1800d56c5  call    cs:__imp_WindowsDeleteString
0x1800d56cb  mov     [rbp+4Fh+var_48], 0
0x1800d56d3  xor     edx, edx; length
0x1800d56d5  mov     rcx, [rbp+4Fh+string]; string
0x1800d56d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d56df  mov     rbx, rax
0x1800d56e2  xor     edx, edx; length
0x1800d56e4  mov     rcx, [rbp+4Fh+var_60]; string
0x1800d56e8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d56ee  lea     rcx, [rbp+4Fh+var_40]
0x1800d56f2  mov     [rsp+0D0h+lpftLastWriteTime], rcx
0x1800d56f7  lea     rcx, [rbp+4Fh+var_48]
0x1800d56fb  mov     [rsp+0D0h+lpcbSecurityDescriptor], rcx
0x1800d5700  mov     dword ptr [rsp+0D0h+lpcbMaxValueLen], 0
0x1800d5708  mov     [rsp+0D0h+lpcbMaxValueNameLen], rdi
0x1800d570d  mov     dword ptr [rsp+0D0h+lpcValues], 0
0x1800d5715  mov     cl, [rbp+4Fh+var_70]
0x1800d5718  mov     byte ptr [rsp+0D0h+lpcbMaxClassLen], cl
0x1800d571c  mov     ecx, [rbp+4Fh+var_50]
0x1800d571f  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], ecx
0x1800d5723  lea     rcx, [rbp+4Fh+var_38]
0x1800d5727  mov     [rsp+0D0h+lpcSubKeys], rcx
0x1800d572c  mov     r9, [rbp+4Fh+arg_8]
0x1800d5730  mov     r8, rbx
0x1800d5733  mov     rdx, rax
0x1800d5736  mov     rcx, r15
0x1800d5739  call    ?SetData@WdcStartupMonitor@@QEAAJPEBG00PEBU_FILETIME@@W4_tagTM_ITEMSTATUS@@_NHPEAUHKEY__@@W4_STARTUP_LOCATION@@PEAPEAUHSTRING__@@PEAPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::SetData(ushort const *,ushort const *,ushort const *,_FILETIME const *,_tagTM_ITEMSTATUS,bool,int,HKEY__ *,_STARTUP_LOCATION,HSTRING__ * *,_WDC_STARTUP_INFO * *)
0x1800d573e  test    eax, eax
0x1800d5740  js      loc_1800D57DA
0x1800d5746  lea     r8, [rbp+4Fh+var_40]
0x1800d574a  mov     rcx, r15
0x1800d574d  call    ?MapStartupProcesses@WdcStartupMonitor@@QEAAJW4_STARTUP_LOCATION@@PEAPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::MapStartupProcesses(_STARTUP_LOCATION,_WDC_STARTUP_INFO * *)
0x1800d5752  mov     rsi, [rbp+4Fh+var_40]
0x1800d5756  mov     byte ptr [rsi+241h], 0
0x1800d575d  mov     [rsi+20h], r13
0x1800d5761  mov     r9, rsi; struct _WDC_STARTUP_INFO *
0x1800d5764  mov     rbx, [rbp+4Fh+var_48]
0x1800d5768  mov     rdx, rbx; HSTRING
0x1800d576b  call    ?_SetIcon@WdcStartupMonitor@@AEAAJPEAUHSTRING__@@_NPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::_SetIcon(HSTRING__ *,bool,_WDC_STARTUP_INFO *)
0x1800d5770  cmp     byte ptr [rsi+242h], 0
0x1800d5777  jz      short loc_1800D5784
0x1800d5779  mov     rdx, rsi; struct _WDC_STARTUP_INFO *
0x1800d577c  mov     rcx, r15; this
0x1800d577f  call    ?DisableItem@WdcStartupMonitor@@QEAAJPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::DisableItem(_WDC_STARTUP_INFO *)
0x1800d5784  mov     rsi, [rbp+4Fh+var_30]
0x1800d5788  inc     r14d
0x1800d578b  cmp     r14d, [rbp+4Fh+cValues]
0x1800d578f  jb      loc_1800D561A
0x1800d5795  mov     edi, [rbp+4Fh+var_68]
0x1800d5798  mov     rcx, rbx; string
0x1800d579b  call    cs:__imp_WindowsDeleteString
0x1800d57a1  xor     r14d, r14d
0x1800d57a4  mov     rcx, [rbp+4Fh+var_60]; string
0x1800d57a8  call    cs:__imp_WindowsDeleteString
0x1800d57ae  mov     [rbp+4Fh+var_60], r14
0x1800d57b2  mov     rcx, [rbp+4Fh+string]; string
0x1800d57b6  call    cs:__imp_WindowsDeleteString
0x1800d57bc  mov     eax, edi
0x1800d57be  lea     r11, [rsp+0D0h+var_20]
0x1800d57c6  mov     rbx, [r11+30h]
0x1800d57ca  mov     rsi, [r11+48h]
0x1800d57ce  mov     rsp, r11
0x1800d57d1  pop     r15
0x1800d57d3  pop     r14
0x1800d57d5  pop     r13
0x1800d57d7  pop     rdi
0x1800d57d8  pop     rbp
0x1800d57d9  retn
0x1800d57da  mov     rbx, [rbp+4Fh+var_48]
0x1800d57de  jmp     short loc_1800D5788
```
