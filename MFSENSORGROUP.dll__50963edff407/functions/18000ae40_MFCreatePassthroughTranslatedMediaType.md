# MFCreatePassthroughTranslatedMediaType

- ea: `0x18000ae40`
- end: `0x18000afa5`
- name: `MFCreatePassthroughTranslatedMediaType`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003be20`
- `0x180059640`

## callees

- `0x180005fa0`
- `0x18000ae14`
- `0x18000ae40`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ae9f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ae9f`

## pseudocode

```c
__int64 __fastcall MFCreatePassthroughTranslatedMediaType(__int64 a1, __int64 a2, __int64 a3)
{
  LPVOID v5; // rcx
  HRESULT v7; // ebx
  int v8; // eax
  LPVOID ppv; // [rsp+78h] [rbp+20h] BYREF

  v5 = 0;
  ppv = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 46, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids);
    v5 = ppv;
  }
  ppv = 0;
  if ( v5 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
  ppv = 0;
  v7 = CoCreateInstance(&CLSID_MFSensorGroupClassFactory, 0, 1u, &GUID_fe4f9dca_ffd8_4d38_932f_282acb3fb775, &ppv);
  if ( v7 < 0 )
  {
    if ( g_wppLevels )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v7);
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v7);
    }
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64))(*(_QWORD *)ppv + 120LL))(ppv, a1, a2, a3);
    v7 = v8;
    if ( v8 < 0 && g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v8);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000ae40  push    rbx
0x18000ae42  push    rbp
0x18000ae43  push    rsi
0x18000ae44  push    rdi
0x18000ae45  sub     rsp, 38h
0x18000ae49  mov     rbp, rcx
0x18000ae4c  mov     rdi, r8
0x18000ae4f  xor     ecx, ecx
0x18000ae51  mov     rsi, rdx
0x18000ae54  mov     [rsp+58h+arg_18], rcx
0x18000ae59  cmp     cs:byte_18008D62D, 8
0x18000ae60  jnb     loc_18000AEF0
0x18000ae66  mov     [rsp+58h+arg_18], 0
0x18000ae6f  test    rcx, rcx
0x18000ae72  jnz     loc_18000AF19
0x18000ae78  xor     edx, edx; pUnkOuter
0x18000ae7a  mov     [rsp+58h+arg_18], 0
0x18000ae83  lea     rax, [rsp+58h+arg_18]
0x18000ae88  lea     r9, _GUID_fe4f9dca_ffd8_4d38_932f_282acb3fb775; riid
0x18000ae8f  mov     [rsp+58h+ppv], rax; ppv
0x18000ae94  lea     rcx, CLSID_MFSensorGroupClassFactory; rclsid
0x18000ae9b  lea     r8d, [rdx+1]; dwClsContext
0x18000ae9f  call    cs:__imp_CoCreateInstance
0x18000aea5  mov     ebx, eax
0x18000aea7  test    eax, eax
0x18000aea9  js      short loc_18000AF2A
0x18000aeab  mov     rcx, [rsp+58h+arg_18]
0x18000aeb0  mov     r9, rdi
0x18000aeb3  mov     r8, rsi
0x18000aeb6  mov     rdx, rbp
0x18000aeb9  mov     rax, [rcx]
0x18000aebc  mov     rax, [rax+78h]
0x18000aec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aec5  mov     ebx, eax
0x18000aec7  test    eax, eax
0x18000aec9  js      loc_18000AF70
0x18000aecf  mov     rcx, [rsp+58h+arg_18]
0x18000aed4  test    rcx, rcx
0x18000aed7  jz      short loc_18000AEE5
0x18000aed9  mov     rax, [rcx]
0x18000aedc  mov     rax, [rax+10h]
0x18000aee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee5  mov     eax, ebx
0x18000aee7  add     rsp, 38h
0x18000aeeb  pop     rdi
0x18000aeec  pop     rsi
0x18000aeed  pop     rbp
0x18000aeee  pop     rbx
0x18000aeef  retn
0x18000aef0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aef7  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18000aefe  mov     edx, 2Eh ; '.'
0x18000af03  mov     rcx, [rcx+0D8h]
0x18000af0a  call    WPP_SF_
0x18000af0f  mov     rcx, [rsp+58h+arg_18]
0x18000af14  jmp     loc_18000AE66
0x18000af19  mov     rax, [rcx]
0x18000af1c  mov     rax, [rax+10h]
0x18000af20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af25  jmp     loc_18000AE78
0x18000af2a  mov     al, cs:?g_wppLevels@@3UMFWppLevels@@A; MFWppLevels g_wppLevels
0x18000af30  cmp     al, 1
0x18000af32  jb      short loc_18000AECF
0x18000af34  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af3b  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18000af42  mov     edx, 0Bh
0x18000af47  mov     dword ptr [rsp+58h+ppv], ebx
0x18000af4b  xor     r9d, r9d
0x18000af4e  mov     rcx, [rcx+10h]
0x18000af52  call    WPP_SF_qD
0x18000af57  mov     al, cs:?g_wppLevels@@3UMFWppLevels@@A; MFWppLevels g_wppLevels
0x18000af5d  cmp     al, 1
0x18000af5f  jb      loc_18000AECF
0x18000af65  mov     edx, 2Fh ; '/'
0x18000af6a  mov     dword ptr [rsp+58h+ppv], ebx
0x18000af6e  jmp     short loc_18000AF86
0x18000af70  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000af77  jb      loc_18000AECF
0x18000af7d  mov     edx, 30h ; '0'
0x18000af82  mov     dword ptr [rsp+58h+ppv], eax
0x18000af86  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af8d  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18000af94  xor     r9d, r9d
0x18000af97  mov     rcx, [rcx+10h]
0x18000af9b  call    WPP_SF_qD
0x18000afa0  jmp     loc_18000AECF
```
