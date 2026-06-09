# SensorProfileCollection::CreateSensorProfileCollection(IMFSensorProfileCollectionInternal * *)

- ea: `0x180028b70`
- end: `0x180028c9f`
- name: `?CreateSensorProfileCollection@SensorProfileCollection@@SAJPEAPEAUIMFSensorProfileCollectionInternal@@@Z`
- size: `303`
- prototype: `__int64 __fastcall(struct IMFSensorProfileCollectionInternal **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800289f0`

## callees

- `0x180005fa0`
- `0x180028b70`
- `0x180028ca8`
- `0x180028d34`
- `0x180044adc`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180028bc3`
- `MFPlat!MFCreateAttributes` at `0x180028bc3`

## pseudocode

```c
__int64 __fastcall SensorProfileCollection::CreateSensorProfileCollection(
        struct IMFSensorProfileCollectionInternal **a1)
{
  SensorProfileCollection *v2; // rax
  SensorProfileCollection *v3; // rax
  IMFAttributes **v4; // rdi
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdx

  if ( !a1 )
  {
    v6 = -2147467261;
    if ( !g_wppLevels )
      return v6;
    v8 = 10;
    goto LABEL_10;
  }
  *a1 = 0;
  v2 = (SensorProfileCollection *)operator new(0x70u);
  if ( !v2 || (v3 = SensorProfileCollection::SensorProfileCollection(v2), (v4 = (IMFAttributes **)v3) == 0) )
  {
    v6 = -2147024882;
    if ( !g_wppLevels )
      return v6;
    v8 = 11;
LABEL_10:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids, 0, v6);
    return v6;
  }
  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset((char *)v3 + 104);
  v5 = MFCreateAttributes(v4 + 13, 1u);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v5 = ((__int64 (__fastcall *)(IMFAttributes **, GUID *, struct IMFSensorProfileCollectionInternal **))(*v4)->lpVtbl)(
           v4,
           &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3,
           a1);
    v6 = v5;
    if ( v5 >= 0 || !g_wppLevels )
      goto LABEL_6;
    v9 = 13;
    goto LABEL_17;
  }
  if ( g_wppLevels )
  {
    v9 = 12;
LABEL_17:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids, 0, v5);
  }
LABEL_6:
  ((void (__fastcall *)(IMFAttributes **))(*v4)[2].lpVtbl)(v4);
  return v6;
}

```

## disassembly

```asm
0x180028b70  mov     [rsp+arg_0], rbx
0x180028b75  mov     [rsp+arg_8], rsi
0x180028b7a  push    rdi
0x180028b7b  sub     rsp, 30h
0x180028b7f  mov     rsi, rcx
0x180028b82  test    rcx, rcx
0x180028b85  jz      loc_180028C45
0x180028b8b  mov     qword ptr [rcx], 0
0x180028b92  mov     ecx, 70h ; 'p'; Size
0x180028b97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180028b9c  test    rax, rax
0x180028b9f  jz      short loc_180028C12
0x180028ba1  mov     rcx, rax; this
0x180028ba4  call    ??0SensorProfileCollection@@IEAA@XZ; SensorProfileCollection::SensorProfileCollection(void)
0x180028ba9  mov     rdi, rax
0x180028bac  test    rax, rax
0x180028baf  jz      short loc_180028C12
0x180028bb1  lea     rcx, [rax+68h]
0x180028bb5  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x180028bba  mov     edx, 1; cInitialSize
0x180028bbf  lea     rcx, [rdi+68h]; ppMFAttributes
0x180028bc3  call    cs:__imp_MFCreateAttributes
0x180028bc9  mov     ebx, eax
0x180028bcb  test    eax, eax
0x180028bcd  js      loc_180028C5A
0x180028bd3  mov     rax, [rdi]
0x180028bd6  lea     rdx, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x180028bdd  mov     r8, rsi
0x180028be0  mov     rcx, rdi
0x180028be3  mov     rax, [rax]
0x180028be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028beb  mov     ebx, eax
0x180028bed  test    eax, eax
0x180028bef  js      short loc_180028C6A
0x180028bf1  mov     rax, [rdi]
0x180028bf4  mov     rcx, rdi
0x180028bf7  mov     rax, [rax+10h]
0x180028bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c00  mov     rsi, [rsp+38h+arg_8]
0x180028c05  mov     eax, ebx
0x180028c07  mov     rbx, [rsp+38h+arg_0]
0x180028c0c  add     rsp, 30h
0x180028c10  pop     rdi
0x180028c11  retn
0x180028c12  mov     ebx, 8007000Eh
0x180028c17  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180028c1e  jb      short loc_180028C00
0x180028c20  mov     edx, 0Bh
0x180028c25  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c2c  lea     r8, WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids
0x180028c33  xor     r9d, r9d
0x180028c36  mov     [rsp+38h+var_18], ebx
0x180028c3a  mov     rcx, [rcx+10h]
0x180028c3e  call    WPP_SF_qD
0x180028c43  jmp     short loc_180028C00
0x180028c45  mov     ebx, 80004003h
0x180028c4a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180028c51  jb      short loc_180028C00
0x180028c53  mov     edx, 0Ah
0x180028c58  jmp     short loc_180028C25
0x180028c5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180028c61  jb      short loc_180028BF1
0x180028c63  mov     edx, 0Ch
0x180028c68  jmp     short loc_180028C7C
0x180028c6a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180028c71  jb      loc_180028BF1
0x180028c77  mov     edx, 0Dh
0x180028c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028c83  lea     r8, WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids
0x180028c8a  xor     r9d, r9d
0x180028c8d  mov     [rsp+38h+var_18], eax
0x180028c91  mov     rcx, [rcx+10h]
0x180028c95  call    WPP_SF_qD
0x180028c9a  jmp     loc_180028BF1
```
