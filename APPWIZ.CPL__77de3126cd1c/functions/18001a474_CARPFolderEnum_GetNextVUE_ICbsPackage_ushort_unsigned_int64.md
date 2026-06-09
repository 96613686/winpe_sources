# CARPFolderEnum::_GetNextVUE(ICbsPackage * *,ushort *,unsigned __int64)

- ea: `0x18001a474`
- end: `0x18001a662`
- name: `?_GetNextVUE@CARPFolderEnum@@AEAAJPEAPEAUICbsPackage@@PEAG_K@Z`
- size: `494`
- prototype: `__int64 __fastcall(CARPFolderEnum *__hidden this, struct ICbsPackage **, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800153d0`

## callees

- `0x180008cf8`
- `0x1800175a0`
- `0x1800185b4`
- `0x18001a474`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a501`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001a501`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a548`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a548`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a63d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a63d`
- `ADVAPI32!RegEnumKeyW` at `0x18001a4cd`
- `ADVAPI32!RegEnumKeyW` at `0x18001a4cd`

## string_xrefs

- `0x18001a51e`: `VUEComponent`

## pseudocode

```c
__int64 __fastcall CARPFolderEnum::_GetNextVUE(CARPFolderEnum *this, struct IUnknown **a2, unsigned __int16 *a3)
{
  int v6; // ebx
  HKEY v7; // rcx
  HKEY v8; // rcx
  LSTATUS ValueW; // eax
  bool v10; // sf
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // edx
  DWORD pcbData[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD pvData[264]; // [rsp+60h] [rbp-A0h] BYREF

  *a3 = 0;
  v6 = 1;
  if ( a2 )
    *a2 = 0;
  v7 = (HKEY)*((_QWORD *)this + 9);
  if ( v7 )
  {
    if ( !RegEnumKeyW(v7, *((_DWORD *)this + 16), a3, 0x104u) )
    {
      v8 = (HKEY)*((_QWORD *)this + 9);
      ++*((_DWORD *)this + 16);
      hkey = 0;
      if ( !RegOpenKeyExW(v8, a3, 0, 0x20019u, &hkey) )
      {
        pcbData[0] = 520;
        ValueW = RegGetValueW(hkey, 0, L"VUEComponent", 2u, 0, pvData, pcbData);
        v10 = ValueW < 0;
        if ( ValueW )
        {
          pvData[0] = 0;
          v10 = ValueW < 0;
          if ( ValueW > 0 )
            v10 = 1;
        }
        if ( !v10 )
        {
          v11 = *((_QWORD *)this + 6);
          *(_QWORD *)pcbData = 0;
          v6 = (*(__int64 (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v11 + 64LL))(v11, pcbData);
          if ( v6 >= 0 )
          {
            v6 = (*(__int64 (__fastcall **)(_QWORD, _WORD *))(**(_QWORD **)pcbData + 56LL))(*(_QWORD *)pcbData, pvData);
            if ( v6 >= 0 )
            {
              v12 = *((_QWORD *)this + 6);
              v17[0] = 0;
              if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD *))(*(_QWORD *)v12 + 48LL))(
                     v12,
                     0,
                     *(_QWORD *)pcbData,
                     0,
                     v17) < 0 )
              {
                v6 = 1;
              }
              else
              {
                v6 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IUnknown **))v17[0])(
                       v17[0],
                       &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed,
                       a2);
                if ( v6 >= 0 )
                {
                  v6 = SetProxyBlanketImpersonationLevelAndDynamicCloaking(*a2, v13);
                  if ( v6 >= 0 )
                    CARPFolderEnum::_AddChildrenToFilterList(this, hkey);
                }
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v17);
            }
          }
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(pcbData);
        }
        RegCloseKey(hkey);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a474  push    rbp
0x18001a476  push    rbx
0x18001a477  push    rsi
0x18001a478  push    rdi
0x18001a479  push    r14
0x18001a47b  lea     rbp, [rsp-180h]
0x18001a483  sub     rsp, 280h
0x18001a48a  mov     rax, cs:__security_cookie
0x18001a491  xor     rax, rsp
0x18001a494  mov     [rbp+1A0h+var_30], rax
0x18001a49b  xor     eax, eax
0x18001a49d  mov     r14, r8
0x18001a4a0  mov     [r8], ax
0x18001a4a4  mov     rsi, rdx
0x18001a4a7  mov     rdi, rcx
0x18001a4aa  mov     ebx, 1
0x18001a4af  test    rdx, rdx
0x18001a4b2  jz      short loc_18001A4B7
0x18001a4b4  mov     [rdx], rax
0x18001a4b7  mov     rcx, [rcx+48h]; hKey
0x18001a4bb  test    rcx, rcx
0x18001a4be  jz      loc_18001A643
0x18001a4c4  mov     edx, [rdi+40h]; dwIndex
0x18001a4c7  mov     r9d, 104h; cchName
0x18001a4cd  call    cs:__imp_RegEnumKeyW
0x18001a4d3  test    eax, eax
0x18001a4d5  jnz     loc_18001A643
0x18001a4db  mov     rcx, [rdi+48h]; hKey
0x18001a4df  lea     rax, [rsp+2A0h+hkey]
0x18001a4e4  inc     dword ptr [rdi+40h]
0x18001a4e7  mov     r9d, 20019h; samDesired
0x18001a4ed  xor     r8d, r8d; ulOptions
0x18001a4f0  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18001a4f5  mov     rdx, r14; lpSubKey
0x18001a4f8  mov     [rsp+2A0h+hkey], 0
0x18001a501  call    cs:__imp_RegOpenKeyExW
0x18001a507  test    eax, eax
0x18001a509  jnz     loc_18001A643
0x18001a50f  mov     rcx, [rsp+2A0h+hkey]; hkey
0x18001a514  lea     rax, [rsp+2A0h+var_260]
0x18001a519  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18001a51e  lea     r8, Value; "VUEComponent"
0x18001a525  lea     rax, [rsp+2A0h+var_240]
0x18001a52a  mov     [rsp+2A0h+var_260], 208h
0x18001a532  mov     [rsp+2A0h+pvData], rax; pvData
0x18001a537  mov     r9d, 2; dwFlags
0x18001a53d  xor     edx, edx; lpSubKey
0x18001a53f  mov     [rsp+2A0h+phkResult], 0; pdwType
0x18001a548  call    cs:__imp_RegGetValueW
0x18001a54e  test    eax, eax
0x18001a550  jz      short loc_18001A567
0x18001a552  xor     ecx, ecx
0x18001a554  mov     [rsp+2A0h+var_240], cx
0x18001a559  test    eax, eax
0x18001a55b  jle     short loc_18001A567
0x18001a55d  movzx   eax, ax
0x18001a560  or      eax, 80070000h
0x18001a565  test    eax, eax
0x18001a567  js      loc_18001A638
0x18001a56d  mov     rcx, [rdi+30h]
0x18001a571  lea     rdx, [rsp+2A0h+var_260]
0x18001a576  mov     qword ptr [rsp+2A0h+var_260], 0
0x18001a57f  mov     rax, [rcx]
0x18001a582  mov     rax, [rax+40h]
0x18001a586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a58b  mov     ebx, eax
0x18001a58d  test    eax, eax
0x18001a58f  js      loc_18001A62E
0x18001a595  mov     rcx, qword ptr [rsp+2A0h+var_260]
0x18001a59a  lea     rdx, [rsp+2A0h+var_240]
0x18001a59f  mov     rax, [rcx]
0x18001a5a2  mov     rax, [rax+38h]
0x18001a5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5ab  mov     ebx, eax
0x18001a5ad  test    eax, eax
0x18001a5af  js      short loc_18001A62E
0x18001a5b1  mov     rcx, [rdi+30h]
0x18001a5b5  lea     rdx, [rsp+2A0h+var_250]
0x18001a5ba  mov     r8, qword ptr [rsp+2A0h+var_260]
0x18001a5bf  xor     r9d, r9d
0x18001a5c2  mov     [rsp+2A0h+var_250], 0
0x18001a5cb  mov     [rsp+2A0h+phkResult], rdx
0x18001a5d0  xor     edx, edx
0x18001a5d2  mov     rax, [rcx]
0x18001a5d5  mov     rax, [rax+30h]
0x18001a5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5de  test    eax, eax
0x18001a5e0  js      short loc_18001A61F
0x18001a5e2  mov     rcx, [rsp+2A0h+var_250]
0x18001a5e7  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x18001a5ee  mov     r8, rsi
0x18001a5f1  mov     rax, [rcx]
0x18001a5f4  mov     rax, [rax]
0x18001a5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5fc  mov     ebx, eax
0x18001a5fe  test    eax, eax
0x18001a600  js      short loc_18001A624
0x18001a602  mov     rcx, [rsi]; struct IUnknown *
0x18001a605  call    ?SetProxyBlanketImpersonationLevelAndDynamicCloaking@@YAJPEAUIUnknown@@K@Z; SetProxyBlanketImpersonationLevelAndDynamicCloaking(IUnknown *,ulong)
0x18001a60a  mov     ebx, eax
0x18001a60c  test    eax, eax
0x18001a60e  js      short loc_18001A624
0x18001a610  mov     rdx, [rsp+2A0h+hkey]; HKEY
0x18001a615  mov     rcx, rdi; this
0x18001a618  call    ?_AddChildrenToFilterList@CARPFolderEnum@@AEAAJPEAUHKEY__@@@Z; CARPFolderEnum::_AddChildrenToFilterList(HKEY__ *)
0x18001a61d  jmp     short loc_18001A624
0x18001a61f  mov     ebx, 1
0x18001a624  lea     rcx, [rsp+2A0h+var_250]
0x18001a629  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001a62e  lea     rcx, [rsp+2A0h+var_260]
0x18001a633  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001a638  mov     rcx, [rsp+2A0h+hkey]; hKey
0x18001a63d  call    cs:__imp_RegCloseKey
0x18001a643  mov     eax, ebx
0x18001a645  mov     rcx, [rbp+1A0h+var_30]
0x18001a64c  xor     rcx, rsp; StackCookie
0x18001a64f  call    __security_check_cookie
0x18001a654  add     rsp, 280h
0x18001a65b  pop     r14
0x18001a65d  pop     rdi
0x18001a65e  pop     rsi
0x18001a65f  pop     rbx
0x18001a660  pop     rbp
0x18001a661  retn
```
