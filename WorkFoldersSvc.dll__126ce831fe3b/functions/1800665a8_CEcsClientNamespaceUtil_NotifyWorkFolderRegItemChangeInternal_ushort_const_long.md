# CEcsClientNamespaceUtil::NotifyWorkFolderRegItemChangeInternal(ushort const *,long)

- ea: `0x1800665a8`
- end: `0x180066760`
- name: `?NotifyWorkFolderRegItemChangeInternal@CEcsClientNamespaceUtil@@CAJPEBGJ@Z`
- size: `440`
- prototype: `static int(const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180066450`

## callees

- `0x180003604`
- `0x180007e10`
- `0x180009158`
- `0x180011314`
- `0x18001133c`
- `0x1800665a8`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066728`
- `SHELL32!SHGetDesktopFolder` at `0x18006664b`
- `SHELL32!SHGetDesktopFolder` at `0x18006664b`
- `SHELL32!SHChangeNotify` at `0x18006671d`
- `SHELL32!SHChangeNotify` at `0x18006671d`
- `SHELL32!__imp_SHFlushSFCache` at `0x180066640`
- `SHELL32!__imp_SHFlushSFCache` at `0x180066640`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CEcsClientNamespaceUtil::NotifyWorkFolderRegItemChangeInternal(
        const unsigned __int16 *a1,
        unsigned int a2)
{
  _DWORD *v4; // rax
  char v5; // al
  HRESULT v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  HRESULT pExceptionObject; // [rsp+40h] [rbp-78h] BYREF
  int v11; // [rsp+44h] [rbp-74h] BYREF
  int v12; // [rsp+48h] [rbp-70h] BYREF
  LPCVOID dwItem1; // [rsp+50h] [rbp-68h] BYREF
  IShellFolder *ppshf; // [rsp+58h] [rbp-60h] BYREF
  const ATL::CAtlException *v15; // [rsp+60h] [rbp-58h] BYREF
  int v16; // [rsp+68h] [rbp-50h] BYREF
  int v17; // [rsp+6Ch] [rbp-4Ch]
  char v18; // [rsp+70h] [rbp-48h]
  const char *v19; // [rsp+78h] [rbp-40h]
  __int64 v20; // [rsp+80h] [rbp-38h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) == 0 )
    {
LABEL_8:
      v5 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, &WPP_de021cd3b4143c96d6c033b7b2075fab_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[17] & 0x800) == 0 || *((_BYTE *)v4 + 65) < 6u )
    goto LABEL_8;
  v5 = 1;
LABEL_9:
  v16 = 0;
  v17 = 577;
  v18 = v5;
  v19 = "CEcsClientNamespaceUtil::NotifyWorkFolderRegItemChangeInternal";
  v20 = 0;
  try
  {
    dwItem1 = 0;
    ppshf = 0;
    SHFlushSFCache();
    v6 = SHGetDesktopFolder(&ppshf);
    v16 = v6;
    if ( v6 < 0 )
    {
      HIWORD(v17) = 593;
      pExceptionObject = v6;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v17) = 593;
    v7 = ((__int64 (__fastcall *)(IShellFolder *, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, LPCVOID *, _QWORD))ppshf->lpVtbl->ParseDisplayName)(
           ppshf,
           0,
           0,
           a1,
           0,
           &dwItem1,
           0);
    v16 = v7;
    if ( v7 < 0 )
    {
      HIWORD(v17) = 602;
      v11 = v7;
      throw (long *)&v11;
    }
    LOWORD(v17) = 602;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, &WPP_de021cd3b4143c96d6c033b7b2075fab_Traceguids, a2);
    }
    SHChangeNotify(a2, 0, dwItem1, 0);
    CoTaskMemFree((LPVOID)dwItem1);
    ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(&ppshf);
  }
  catch ( long v12 )
  {
    v16 = v12;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v17) = 615;
    v16 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v17) = 615;
    v16 = -2147418113;
  }
  catch ( const ATL::CAtlException *v15 )
  {
    HIWORD(v17) = 615;
    v16 = *(_DWORD *)v15;
  }
  v8 = v16;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v16);
  return v8;
}

```

## disassembly

```asm
0x1800665a8  push    rbx
0x1800665aa  push    rsi
0x1800665ab  push    r14
0x1800665ad  push    r15
0x1800665af  sub     rsp, 98h
0x1800665b6  mov     esi, edx
0x1800665b8  mov     r14, rcx
0x1800665bb  lea     r15, WPP_GLOBAL_Control
0x1800665c2  mov     rax, cs:WPP_GLOBAL_Control
0x1800665c9  cmp     rax, r15
0x1800665cc  jz      short loc_1800665F9
0x1800665ce  test    dword ptr [rax+44h], 800h
0x1800665d5  jz      short loc_18006660E
0x1800665d7  cmp     byte ptr [rax+41h], 6
0x1800665db  jb      short loc_1800665F9
0x1800665dd  mov     edx, 1Eh
0x1800665e2  lea     r8, WPP_de021cd3b4143c96d6c033b7b2075fab_Traceguids
0x1800665e9  mov     rcx, [rax+38h]
0x1800665ed  call    WPP_SF_
0x1800665f2  mov     rax, cs:WPP_GLOBAL_Control
0x1800665f9  test    dword ptr [rax+44h], 800h
0x180066600  jz      short loc_18006660E
0x180066602  cmp     byte ptr [rax+41h], 6
0x180066606  jb      short loc_18006660E
0x180066608  mov     al, 1
0x18006660a  xor     ebx, ebx
0x18006660c  jmp     short loc_180066612
0x18006660e  xor     ebx, ebx
0x180066610  mov     al, bl
0x180066612  mov     [rsp+0B8h+var_50], ebx
0x180066616  mov     [rsp+0B8h+var_4C], 241h
0x18006661e  mov     [rsp+0B8h+var_48], al
0x180066622  lea     rax, aCecsclientname; "CEcsClientNamespaceUtil::NotifyWorkFold"...
0x180066629  mov     [rsp+0B8h+var_40], rax
0x18006662e  mov     [rsp+0B8h+var_38], rbx
0x180066636  mov     [rsp+0B8h+dwItem1], rbx
0x18006663b  mov     [rsp+0B8h+ppshf], rbx
0x180066640  call    cs:__imp_SHFlushSFCache
0x180066646  lea     rcx, [rsp+0B8h+ppshf]; ppshf
0x18006664b  call    cs:__imp_SHGetDesktopFolder
0x180066651  mov     [rsp+0B8h+var_50], eax
0x180066655  mov     [rsp+0B8h+var_50], eax
0x180066659  mov     ecx, 251h
0x18006665e  test    eax, eax
0x180066660  jns     short loc_18006667C
0x180066662  mov     word ptr [rsp+0B8h+var_4C+2], cx
0x180066667  mov     [rsp+0B8h+pExceptionObject], eax
0x18006666b  lea     rdx, _TI1J; pThrowInfo
0x180066672  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180066677  call    _CxxThrowException_0
0x18006667c  mov     word ptr [rsp+0B8h+var_4C], cx
0x180066681  mov     rcx, [rsp+0B8h+ppshf]
0x180066686  mov     rax, [rcx]
0x180066689  mov     [rsp+0B8h+var_88], rbx
0x18006668e  lea     rdx, [rsp+0B8h+dwItem1]
0x180066693  mov     [rsp+0B8h+var_90], rdx
0x180066698  mov     [rsp+0B8h+var_98], rbx
0x18006669d  mov     r9, r14
0x1800666a0  xor     r8d, r8d
0x1800666a3  xor     edx, edx
0x1800666a5  mov     rax, [rax+18h]
0x1800666a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666ae  mov     [rsp+0B8h+var_50], eax
0x1800666b2  mov     [rsp+0B8h+var_50], eax
0x1800666b6  mov     ecx, 25Ah
0x1800666bb  test    eax, eax
0x1800666bd  jns     short loc_1800666D9
0x1800666bf  mov     word ptr [rsp+0B8h+var_4C+2], cx
0x1800666c4  mov     [rsp+0B8h+var_74], eax
0x1800666c8  lea     rdx, _TI1J; pThrowInfo
0x1800666cf  lea     rcx, [rsp+0B8h+var_74]; pExceptionObject
0x1800666d4  call    _CxxThrowException_0
0x1800666d9  mov     word ptr [rsp+0B8h+var_4C], cx
0x1800666de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800666e5  cmp     rcx, r15
0x1800666e8  jz      short loc_180066711
0x1800666ea  test    dword ptr [rcx+44h], 800h
0x1800666f1  jz      short loc_180066711
0x1800666f3  cmp     byte ptr [rcx+41h], 4
0x1800666f7  jb      short loc_180066711
0x1800666f9  mov     edx, 1Fh
0x1800666fe  mov     r9d, esi
0x180066701  lea     r8, WPP_de021cd3b4143c96d6c033b7b2075fab_Traceguids
0x180066708  mov     rcx, [rcx+38h]
0x18006670c  call    WPP_SF_d
0x180066711  xor     r9d, r9d; dwItem2
0x180066714  mov     r8, [rsp+0B8h+dwItem1]; dwItem1
0x180066719  xor     edx, edx; uFlags
0x18006671b  mov     ecx, esi; wEventId
0x18006671d  call    cs:__imp_SHChangeNotify
0x180066723  mov     rcx, [rsp+0B8h+dwItem1]; pv
0x180066728  call    cs:__imp_CoTaskMemFree
0x18006672e  nop
0x18006672f  lea     rcx, [rsp+0B8h+ppshf]
0x180066734  call    ??1?$CComPtr@UICloudFileInfoFromDisk@@@ATL@@QEAA@XZ; ATL::CComPtr<ICloudFileInfoFromDisk>::~CComPtr<ICloudFileInfoFromDisk>(void)
0x180066739  nop
0x18006673a  jmp     short loc_180066742
0x18006673c  jmp     short loc_180066742
0x18006673e  jmp     short loc_180066742
0x180066740  jmp     short $+2
0x180066742  mov     ebx, [rsp+0B8h+var_50]
0x180066746  lea     rcx, [rsp+0B8h+var_50]; this
0x18006674b  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x180066750  mov     eax, ebx
0x180066752  add     rsp, 98h
0x180066759  pop     r15
0x18006675b  pop     r14
0x18006675d  pop     rsi
0x18006675e  pop     rbx
0x18006675f  retn
```
