# CAudioDeviceManager::SetDefaultEndpointWNFSate(IMMDevice *)

- ea: `0x18001fcb0`
- end: `0x18001ff31`
- name: `?SetDefaultEndpointWNFSate@CAudioDeviceManager@@AEAAXPEAUIMMDevice@@@Z`
- size: `641`
- prototype: `void __fastcall(CAudioDeviceManager *__hidden this, struct IMMDevice *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003630`
- `0x18001fbe0`

## callees

- `0x18001fcb0`
- `0x180029024`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18001febe`
- `ntdll!RtlPublishWnfStateData` at `0x18001febe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fd38`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001fd38`
- `api-ms-win-audiocore-spatial-config-l1-1-0!Create_SpatialAudioDevicePropertyReader` at `0x18001fdc7`
- `api-ms-win-audiocore-spatial-config-l1-1-0!Create_SpatialAudioDevicePropertyReader` at `0x18001fdc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CAudioDeviceManager::SetDefaultEndpointWNFSate(CAudioDeviceManager *this, struct IMMDevice *a2)
{
  int v2; // ebx
  __int64 v3; // [rsp+30h] [rbp-39h] BYREF
  int v4; // [rsp+38h] [rbp-31h] BYREF
  int v5; // [rsp+3Ch] [rbp-2Dh] BYREF
  __int64 v6; // [rsp+40h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v8; // [rsp+58h] [rbp-11h]
  int v9; // [rsp+60h] [rbp-9h] BYREF
  __int64 v10; // [rsp+64h] [rbp-5h]
  __int64 v11; // [rsp+6Ch] [rbp+3h] BYREF
  _QWORD v12[2]; // [rsp+74h] [rbp+Bh] BYREF
  _QWORD v13[2]; // [rsp+84h] [rbp+1Bh] BYREF
  _QWORD v14[3]; // [rsp+94h] [rbp+2Bh] BYREF

  v6 = 0;
  v3 = 0;
  v10 = 0;
  v11 = 0;
  v12[0] = 0;
  v12[1] = 0;
  v13[0] = 0;
  v13[1] = 0;
  v14[0] = 0;
  v14[1] = 0;
  v4 = 0;
  v5 = 0;
  *(_OWORD *)pvar = 0;
  v8 = 0;
  v9 = 1;
  v2 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))a2->lpVtbl->OpenPropertyStore)(a2, 0, &v6);
  if ( v2 >= 0 )
  {
    LODWORD(v10) = (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v6 + 40LL))(
                     v6,
                     &PKEY_AudioEndpoint_FormFactor,
                     pvar) >= 0
                && LOWORD(pvar[0]) == 19
                 ? LODWORD(pvar[1])
                 : 10;
    v2 = Create_SpatialAudioDevicePropertyReader(0, v6, &v3);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 112LL))(v3, &v11);
      if ( v2 >= 0 )
      {
        v2 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v3 + 160LL))(v3, v12);
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v3 + 168LL))(v3, v13);
          if ( v2 >= 0 )
          {
            v2 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v3 + 176LL))(v3, v14);
            if ( v2 >= 0 )
            {
              v2 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v3 + 184LL))(v3, &v4);
              if ( v2 >= 0 )
              {
                HIDWORD(v11) = v4;
                v2 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v3 + 136LL))(v3, &v5);
                if ( v2 >= 0 )
                {
                  HIDWORD(v10) = v5;
                  v2 = RtlPublishWnfStateData(WNF_AUDC_DEFAULT_RENDER_ENDPOINT_PROPERTIES, 0, &v9, 68) | 0x10000000;
                }
              }
            }
          }
        }
      }
    }
  }
  PropVariantClear(pvar);
  if ( v2 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids);
  }
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
}

```

## disassembly

```asm
0x18001fcb0  mov     [rsp-8+arg_0], rbx
0x18001fcb5  mov     [rsp-8+arg_10], rdi
0x18001fcba  push    rbp
0x18001fcbb  lea     rbp, [rsp-57h]
0x18001fcc0  sub     rsp, 0C0h
0x18001fcc7  mov     rax, cs:__security_cookie
0x18001fcce  xor     rax, rsp
0x18001fcd1  mov     [rbp+57h+var_10], rax
0x18001fcd5  mov     rcx, rdx
0x18001fcd8  xor     edi, edi
0x18001fcda  mov     [rbp+57h+var_80], rdi
0x18001fcde  mov     [rbp+57h+var_90], rdi
0x18001fce2  mov     [rbp+57h+var_5C], rdi
0x18001fce6  mov     [rbp+57h+var_54], rdi
0x18001fcea  mov     [rbp+57h+var_4C], rdi
0x18001fcee  mov     [rbp+57h+var_44], rdi
0x18001fcf2  mov     [rbp+57h+var_3C], rdi
0x18001fcf6  mov     [rbp+57h+var_34], rdi
0x18001fcfa  mov     [rbp+57h+var_2C], rdi
0x18001fcfe  mov     [rbp+57h+var_24], rdi
0x18001fd02  mov     [rbp+57h+var_88], edi
0x18001fd05  mov     [rbp+57h+var_84], edi
0x18001fd08  xorps   xmm0, xmm0
0x18001fd0b  xor     eax, eax
0x18001fd0d  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18001fd11  mov     [rbp+57h+var_68], rax
0x18001fd15  mov     [rbp+57h+var_60], 1
0x18001fd1c  mov     rax, [rdx]
0x18001fd1f  lea     r8, [rbp+57h+var_80]
0x18001fd23  xor     edx, edx
0x18001fd25  mov     rax, [rax+20h]
0x18001fd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd2e  mov     ebx, eax
0x18001fd30  test    eax, eax
0x18001fd32  jns     short loc_18001FD93
0x18001fd34  lea     rcx, [rbp+57h+pvar]; pvar
0x18001fd38  call    cs:__imp_PropVariantClear
0x18001fd3e  test    ebx, ebx
0x18001fd40  js      loc_18001FEE5
0x18001fd46  mov     rcx, [rbp+57h+var_90]
0x18001fd4a  test    rcx, rcx
0x18001fd4d  jz      short loc_18001FD5C
0x18001fd4f  mov     rax, [rcx]
0x18001fd52  mov     rax, [rax+10h]
0x18001fd56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd5b  nop
0x18001fd5c  mov     rcx, [rbp+57h+var_80]
0x18001fd60  test    rcx, rcx
0x18001fd63  jz      short loc_18001FD72
0x18001fd65  mov     rax, [rcx]
0x18001fd68  mov     rax, [rax+10h]
0x18001fd6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd71  nop
0x18001fd72  mov     rcx, [rbp+57h+var_10]
0x18001fd76  xor     rcx, rsp; StackCookie
0x18001fd79  call    __security_check_cookie
0x18001fd7e  lea     r11, [rsp+0C0h+var_s0]
0x18001fd86  mov     rbx, [r11+10h]
0x18001fd8a  mov     rdi, [r11+20h]
0x18001fd8e  mov     rsp, r11
0x18001fd91  pop     rbp
0x18001fd92  retn
0x18001fd93  mov     rcx, [rbp+57h+var_80]
0x18001fd97  mov     rax, [rcx]
0x18001fd9a  lea     r8, [rbp+57h+pvar]
0x18001fd9e  lea     rdx, PKEY_AudioEndpoint_FormFactor
0x18001fda5  mov     rax, [rax+28h]
0x18001fda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdae  test    eax, eax
0x18001fdb0  jns     loc_18001FECF
0x18001fdb6  mov     dword ptr [rbp+57h+var_5C], 0Ah
0x18001fdbd  lea     r8, [rbp+57h+var_90]
0x18001fdc1  mov     rdx, [rbp+57h+var_80]
0x18001fdc5  xor     ecx, ecx
0x18001fdc7  call    cs:__imp_Create_SpatialAudioDevicePropertyReader
0x18001fdcd  mov     ebx, eax
0x18001fdcf  test    eax, eax
0x18001fdd1  js      loc_18001FD34
0x18001fdd7  mov     rcx, [rbp+57h+var_90]
0x18001fddb  mov     rax, [rcx]
0x18001fdde  lea     rdx, [rbp+57h+var_54]
0x18001fde2  mov     rax, [rax+70h]
0x18001fde6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdeb  mov     ebx, eax
0x18001fded  test    eax, eax
0x18001fdef  js      loc_18001FD34
0x18001fdf5  mov     rcx, [rbp+57h+var_90]
0x18001fdf9  mov     rax, [rcx]
0x18001fdfc  lea     rdx, [rbp+57h+var_4C]
0x18001fe00  mov     rax, [rax+0A0h]
0x18001fe07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe0c  mov     ebx, eax
0x18001fe0e  test    eax, eax
0x18001fe10  js      loc_18001FD34
0x18001fe16  mov     rcx, [rbp+57h+var_90]
0x18001fe1a  mov     rax, [rcx]
0x18001fe1d  lea     rdx, [rbp+57h+var_3C]
0x18001fe21  mov     rax, [rax+0A8h]
0x18001fe28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe2d  mov     ebx, eax
0x18001fe2f  test    eax, eax
0x18001fe31  js      loc_18001FD34
0x18001fe37  mov     rcx, [rbp+57h+var_90]
0x18001fe3b  mov     rax, [rcx]
0x18001fe3e  lea     rdx, [rbp+57h+var_2C]
0x18001fe42  mov     rax, [rax+0B0h]
0x18001fe49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe4e  mov     ebx, eax
0x18001fe50  test    eax, eax
0x18001fe52  js      loc_18001FD34
0x18001fe58  mov     rcx, [rbp+57h+var_90]
0x18001fe5c  mov     rax, [rcx]
0x18001fe5f  lea     rdx, [rbp+57h+var_88]
0x18001fe63  mov     rax, [rax+0B8h]
0x18001fe6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe6f  mov     ebx, eax
0x18001fe71  test    eax, eax
0x18001fe73  js      loc_18001FD34
0x18001fe79  mov     eax, [rbp+57h+var_88]
0x18001fe7c  mov     dword ptr [rbp+57h+var_54+4], eax
0x18001fe7f  mov     rcx, [rbp+57h+var_90]
0x18001fe83  mov     rax, [rcx]
0x18001fe86  lea     rdx, [rbp+57h+var_84]
0x18001fe8a  mov     rax, [rax+88h]
0x18001fe91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe96  mov     ebx, eax
0x18001fe98  test    eax, eax
0x18001fe9a  js      loc_18001FD34
0x18001fea0  mov     eax, [rbp+57h+var_84]
0x18001fea3  mov     dword ptr [rbp+57h+var_5C+4], eax
0x18001fea6  mov     [rsp+0C0h+var_A0], rdi
0x18001feab  mov     r9d, 44h ; 'D'
0x18001feb1  lea     r8, [rbp+57h+var_60]
0x18001feb5  xor     edx, edx
0x18001feb7  mov     rcx, cs:WNF_AUDC_DEFAULT_RENDER_ENDPOINT_PROPERTIES
0x18001febe  call    cs:__imp_RtlPublishWnfStateData
0x18001fec4  mov     ebx, eax
0x18001fec6  bts     ebx, 1Ch
0x18001feca  jmp     loc_18001FD34
0x18001fecf  cmp     word ptr [rbp+57h+pvar], 13h
0x18001fed4  jnz     loc_18001FDB6
0x18001feda  mov     eax, dword ptr [rbp+57h+pvar+8]
0x18001fedd  mov     dword ptr [rbp+57h+var_5C], eax
0x18001fee0  jmp     loc_18001FDBD
0x18001fee5  lea     rax, WPP_GLOBAL_Control
0x18001feec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fef3  cmp     rcx, rax
0x18001fef6  jz      loc_18001FD46
0x18001fefc  test    dword ptr [rcx+1Ch], 80000h
0x18001ff03  jz      loc_18001FD46
0x18001ff09  cmp     byte ptr [rcx+19h], 2
0x18001ff0d  jb      loc_18001FD46
0x18001ff13  mov     edx, 33h ; '3'
0x18001ff18  mov     r9d, ebx
0x18001ff1b  lea     r8, WPP_8ed034b4a8dd37d32badf863e188f6d1_Traceguids
0x18001ff22  mov     rcx, [rcx+10h]
0x18001ff26  call    WPP_SF_d
0x18001ff2b  jmp     loc_18001FD46
```
