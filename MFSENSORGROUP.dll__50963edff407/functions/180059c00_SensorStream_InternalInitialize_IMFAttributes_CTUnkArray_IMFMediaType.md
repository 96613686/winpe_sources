# SensorStream::InternalInitialize(IMFAttributes *,CTUnkArray<IMFMediaType> &)

- ea: `0x180059c00`
- end: `0x180059de0`
- name: `?InternalInitialize@SensorStream@@MEAAJPEAUIMFAttributes@@AEAV?$CTUnkArray@UIMFMediaType@@@@@Z`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x180008fe4`
- `0x18001ee8c`
- `0x180059c00`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180059c9b`
- `MFPlat!MFCreateAttributes` at `0x180059c9b`

## pseudocode

```c
__int64 __fastcall SensorStream::InternalInitialize(__int64 a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  unsigned int v7; // ebx
  UINT32 v8; // edx
  HRESULT v9; // eax
  __int64 v10; // rdx
  UINT32 cInitialSize; // [rsp+60h] [rbp+30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+68h] [rbp+38h] BYREF

  v3 = *(_DWORD *)(a3 + 8) == 0;
  cInitialSize = 0;
  ppMFAttributes = 0;
  if ( v3 )
  {
    v7 = -1072875852;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids,
        a1,
        -1072875852);
    goto LABEL_27;
  }
  if ( a2 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)a2 + 240LL))(a2, &cInitialSize);
    v7 = v9;
    if ( v9 < 0 )
    {
      if ( g_wppLevels )
      {
        v10 = 25;
LABEL_26:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, a1, v9);
        goto LABEL_27;
      }
      goto LABEL_27;
    }
    v8 = cInitialSize;
  }
  else
  {
    v8 = 2;
    cInitialSize = 2;
  }
  v9 = MFCreateAttributes(&ppMFAttributes, v8);
  v7 = v9;
  if ( v9 >= 0 )
  {
    if ( a2 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)a2 + 256LL))(a2, ppMFAttributes);
      v7 = v9;
      if ( v9 < 0 )
      {
        if ( g_wppLevels )
        {
          v10 = 29;
          goto LABEL_26;
        }
        goto LABEL_27;
      }
    }
    else
    {
      v9 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, GUID *))ppMFAttributes->lpVtbl->SetGUID)(
             ppMFAttributes,
             &MF_DEVICESTREAM_STREAM_CATEGORY,
             &GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba);
      v7 = v9;
      if ( v9 < 0 )
      {
        if ( g_wppLevels )
        {
          v10 = 27;
          goto LABEL_26;
        }
        goto LABEL_27;
      }
      v9 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, _QWORD))ppMFAttributes->lpVtbl->SetUINT32)(
             ppMFAttributes,
             &MF_DEVICESTREAM_STREAM_ID,
             *(unsigned int *)(a1 + 56));
      v7 = v9;
      if ( v9 < 0 )
      {
        if ( g_wppLevels )
        {
          v10 = 28;
          goto LABEL_26;
        }
        goto LABEL_27;
      }
    }
    v9 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *, __int64))(*(_QWORD *)a1 + 376LL))(a1, ppMFAttributes, a3);
    v7 = v9;
    if ( v9 >= 0 )
    {
      ComSmartPtr<IMFAttributes>::operator=((_QWORD *)(a1 + 64), &ppMFAttributes);
      goto LABEL_29;
    }
    if ( g_wppLevels )
    {
      v10 = 30;
      goto LABEL_26;
    }
    goto LABEL_27;
  }
  if ( g_wppLevels )
  {
    v10 = 26;
    goto LABEL_26;
  }
LABEL_27:
  CTUnkArray<IMFSensorDeviceIdInternal>::RemoveAll(a1 + 72);
LABEL_29:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  return v7;
}

```

## disassembly

```asm
0x180059c00  mov     [rsp-18h+arg_0], rbx
0x180059c05  mov     [rsp-18h+arg_8], rsi
0x180059c0a  push    rbp
0x180059c0b  push    rdi
0x180059c0c  push    r14
0x180059c0e  mov     rbp, rsp
0x180059c11  sub     rsp, 30h
0x180059c15  cmp     dword ptr [r8+8], 0
0x180059c1a  mov     r14, r8
0x180059c1d  mov     rsi, rdx
0x180059c20  mov     [rbp+cInitialSize], 0
0x180059c27  mov     rdi, rcx
0x180059c2a  mov     [rbp+ppMFAttributes], 0
0x180059c32  jnz     short loc_180059C54
0x180059c34  mov     ebx, 0C00D36B4h
0x180059c39  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059c40  jb      loc_180059DAA
0x180059c46  mov     edx, 18h
0x180059c4b  mov     [rsp+30h+var_10], ebx
0x180059c4f  jmp     loc_180059D90
0x180059c54  test    rsi, rsi
0x180059c57  jnz     short loc_180059C61
0x180059c59  lea     edx, [rsi+2]
0x180059c5c  mov     [rbp+cInitialSize], edx
0x180059c5f  jmp     short loc_180059C97
0x180059c61  mov     rax, [rdx]
0x180059c64  mov     rcx, rsi
0x180059c67  lea     rdx, [rbp+cInitialSize]
0x180059c6b  mov     rax, [rax+0F0h]
0x180059c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c77  mov     ebx, eax
0x180059c79  test    eax, eax
0x180059c7b  jns     short loc_180059C94
0x180059c7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059c84  jb      loc_180059DAA
0x180059c8a  mov     edx, 19h
0x180059c8f  jmp     loc_180059D8C
0x180059c94  mov     edx, [rbp+cInitialSize]; cInitialSize
0x180059c97  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180059c9b  call    cs:__imp_MFCreateAttributes
0x180059ca1  mov     ebx, eax
0x180059ca3  test    eax, eax
0x180059ca5  jns     short loc_180059CBE
0x180059ca7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059cae  jb      loc_180059DAA
0x180059cb4  mov     edx, 1Ah
0x180059cb9  jmp     loc_180059D8C
0x180059cbe  test    rsi, rsi
0x180059cc1  jnz     short loc_180059D33
0x180059cc3  mov     rcx, [rbp+ppMFAttributes]
0x180059cc7  lea     r8, _GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba
0x180059cce  lea     rdx, MF_DEVICESTREAM_STREAM_CATEGORY
0x180059cd5  mov     rax, [rcx]
0x180059cd8  mov     rax, [rax+0C0h]
0x180059cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ce4  mov     ebx, eax
0x180059ce6  test    eax, eax
0x180059ce8  jns     short loc_180059CFF
0x180059cea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059cf1  jb      loc_180059DAA
0x180059cf7  lea     edx, [rsi+1Bh]
0x180059cfa  jmp     loc_180059D8C
0x180059cff  mov     rcx, [rbp+ppMFAttributes]
0x180059d03  lea     rdx, MF_DEVICESTREAM_STREAM_ID
0x180059d0a  mov     r8d, [rdi+38h]
0x180059d0e  mov     rax, [rcx]
0x180059d11  mov     rax, [rax+0A8h]
0x180059d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d1d  mov     ebx, eax
0x180059d1f  test    eax, eax
0x180059d21  jns     short loc_180059D5F
0x180059d23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059d2a  jb      short loc_180059DAA
0x180059d2c  mov     edx, 1Ch
0x180059d31  jmp     short loc_180059D8C
0x180059d33  mov     rax, [rsi]
0x180059d36  mov     rcx, rsi
0x180059d39  mov     rdx, [rbp+ppMFAttributes]
0x180059d3d  mov     rax, [rax+100h]
0x180059d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d49  mov     ebx, eax
0x180059d4b  test    eax, eax
0x180059d4d  jns     short loc_180059D5F
0x180059d4f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059d56  jb      short loc_180059DAA
0x180059d58  mov     edx, 1Dh
0x180059d5d  jmp     short loc_180059D8C
0x180059d5f  mov     rax, [rdi]
0x180059d62  mov     r8, r14
0x180059d65  mov     rdx, [rbp+ppMFAttributes]
0x180059d69  mov     rcx, rdi
0x180059d6c  mov     rax, [rax+178h]
0x180059d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d78  mov     ebx, eax
0x180059d7a  test    eax, eax
0x180059d7c  jns     short loc_180059DB5
0x180059d7e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059d85  jb      short loc_180059DAA
0x180059d87  mov     edx, 1Eh
0x180059d8c  mov     [rsp+30h+var_10], eax
0x180059d90  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d97  lea     r8, WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids
0x180059d9e  mov     r9, rdi
0x180059da1  mov     rcx, [rcx+10h]
0x180059da5  call    WPP_SF_qD
0x180059daa  lea     rcx, [rdi+48h]
0x180059dae  call    ?RemoveAll@?$CTUnkArray@UIMFSensorDeviceIdInternal@@@@QEAAXXZ; CTUnkArray<IMFSensorDeviceIdInternal>::RemoveAll(void)
0x180059db3  jmp     short loc_180059DC2
0x180059db5  lea     rcx, [rdi+40h]
0x180059db9  lea     rdx, [rbp+ppMFAttributes]
0x180059dbd  call    ??4?$ComSmartPtr@UIMFAttributes@@@@QEAAPEAUIMFAttributes@@AEBV0@@Z; ComSmartPtr<IMFAttributes>::operator=(ComSmartPtr<IMFAttributes> const &)
0x180059dc2  lea     rcx, [rbp+ppMFAttributes]
0x180059dc6  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180059dcb  mov     rsi, [rsp+30h+arg_8]
0x180059dd0  mov     eax, ebx
0x180059dd2  mov     rbx, [rsp+30h+arg_0]
0x180059dd7  add     rsp, 30h
0x180059ddb  pop     r14
0x180059ddd  pop     rdi
0x180059dde  pop     rbp
0x180059ddf  retn
```
