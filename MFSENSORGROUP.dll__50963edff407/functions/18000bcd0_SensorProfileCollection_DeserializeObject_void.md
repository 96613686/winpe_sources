# SensorProfileCollection::DeserializeObject(void)

- ea: `0x18000bcd0`
- end: `0x18000bfd5`
- name: `?DeserializeObject@SensorProfileCollection@@UEAAJXZ`
- size: `773`
- prototype: `__int64 __fastcall(SensorProfileCollection *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x180009a20`
- `0x18000bcd0`
- `0x18000bfdc`
- `0x18000c284`
- `0x18000c2ec`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000be12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000be12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bceb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bceb`
- `MFPlat!MFInitAttributesFromBlob` at `0x18000bf1e`
- `MFPlat!MFInitAttributesFromBlob` at `0x18000bf1e`

## pseudocode

```c
__int64 __fastcall SensorProfileCollection::DeserializeObject(SensorProfileCollection *this)
{
  _DWORD *v2; // r15
  _DWORD *v3; // r14
  unsigned int v4; // ebp
  HRESULT v5; // eax
  unsigned int v6; // esi
  UINT v7; // r8d
  unsigned int i; // r14d
  unsigned int v9; // edx
  unsigned __int8 *v10; // rcx
  int v11; // eax
  __int64 v12; // r13
  struct IMFSensorProfileInternal *v13; // rsi
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  unsigned int v18; // [rsp+70h] [rbp+8h] BYREF
  struct IMFSensorProfileInternal *v19; // [rsp+78h] [rbp+10h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v2 = (_DWORD *)*((_QWORD *)this + 11);
  v3 = (_DWORD *)((char *)this + 96);
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qqD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      43,
      &WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids,
      this,
      v2,
      *v3);
  if ( !*((_QWORD *)this + 11) )
  {
    v6 = -1072875850;
    if ( !g_wppLevels )
      goto LABEL_20;
    v16 = 44;
    goto LABEL_28;
  }
  v4 = 16;
  if ( *v3 < 0x10u )
  {
    v6 = -1072860816;
    if ( !g_wppLevels )
      goto LABEL_20;
    v16 = 45;
LABEL_28:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids, this, v6);
    goto LABEL_20;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 160LL))(*((_QWORD *)this + 13));
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_20;
    v17 = 46;
    goto LABEL_32;
  }
  v7 = v2[3];
  if ( !v7 || *v3 - 16 < v7 )
  {
LABEL_7:
    CTUnkArray<IMFSensorProfileInternal>::RemoveAll((char *)this + 64);
    for ( i = 0; i < v2[2]; ++i )
    {
      v9 = *((_DWORD *)this + 24);
      if ( v9 <= v4 )
        break;
      v10 = (unsigned __int8 *)(*((_QWORD *)this + 11) + v4);
      v18 = 0;
      v19 = 0;
      v11 = SensorProfile::LoadSensorProfile(v10, v9 - v4, &v18, &v19);
      v6 = v11;
      if ( v11 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            &WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids,
            this,
            v11);
        if ( v19 )
          (*(void (__fastcall **)(struct IMFSensorProfileInternal *))(*(_QWORD *)v19 + 16LL))(v19);
        goto LABEL_20;
      }
      v12 = *((unsigned int *)this + 18);
      v13 = v19;
      if ( !(unsigned int)CTEntryArray<SensorDeviceId *>::SetSize((char *)this + 64, (unsigned int)(v12 + 1)) )
      {
        v6 = -2147024882;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            &WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids,
            this,
            -2147024882);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v19);
        goto LABEL_20;
      }
      *(_QWORD *)(*((_QWORD *)this + 8) + 8 * v12) = v13;
      if ( v13 )
        (*(void (__fastcall **)(struct IMFSensorProfileInternal *))(*(_QWORD *)v13 + 8LL))(v13);
      v4 += v18;
      if ( v19 )
        (*(void (__fastcall **)(struct IMFSensorProfileInternal *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    *((_DWORD *)this + 25) = v2[1];
    v6 = 0;
    if ( (unsigned __int8)byte_18008D62D < 8u )
      goto LABEL_18;
    v15 = 52;
    goto LABEL_42;
  }
  v5 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 13), (const UINT8 *)(*((_QWORD *)this + 11) + 16LL), v7);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v4 = v2[3] + 16;
    goto LABEL_7;
  }
  if ( g_wppLevels )
  {
    v17 = 47;
LABEL_32:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids, this, v5);
  }
LABEL_20:
  if ( byte_18008D62D )
  {
    v15 = 51;
LABEL_42:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v15, &WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids, this, v6);
  }
LABEL_18:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v6;
}

```

## disassembly

```asm
0x18000bcd0  mov     [rsp+arg_10], rbx
0x18000bcd5  push    rbp
0x18000bcd6  push    rsi
0x18000bcd7  push    rdi
0x18000bcd8  push    r12
0x18000bcda  push    r13
0x18000bcdc  push    r14
0x18000bcde  push    r15
0x18000bce0  sub     rsp, 30h
0x18000bce4  mov     rdi, rcx
0x18000bce7  add     rcx, 18h; lpCriticalSection
0x18000bceb  call    cs:__imp_EnterCriticalSection
0x18000bcf1  mov     r15, [rdi+58h]
0x18000bcf5  cmp     cs:byte_18008D62D, 8
0x18000bcfc  lea     r14, [rdi+60h]
0x18000bd00  jnb     loc_18000BE32
0x18000bd06  cmp     qword ptr [rdi+58h], 0
0x18000bd0b  jz      loc_18000BE81
0x18000bd11  mov     ebp, 10h
0x18000bd16  cmp     [r14], ebp
0x18000bd19  jb      loc_18000BEC6
0x18000bd1f  mov     rcx, [rdi+68h]
0x18000bd23  mov     rax, [rcx]
0x18000bd26  mov     rax, [rax+0A0h]
0x18000bd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd32  mov     esi, eax
0x18000bd34  test    eax, eax
0x18000bd36  js      loc_18000BE65
0x18000bd3c  mov     r8d, [r15+0Ch]; cbBufSize
0x18000bd40  test    r8d, r8d
0x18000bd43  jnz     loc_18000BF05
0x18000bd49  lea     rcx, [rdi+40h]
0x18000bd4d  call    ?RemoveAll@?$CTUnkArray@UIMFSensorProfileInternal@@@@QEAAXXZ; CTUnkArray<IMFSensorProfileInternal>::RemoveAll(void)
0x18000bd52  xor     r14d, r14d
0x18000bd55  cmp     r14d, [r15+8]
0x18000bd59  jnb     loc_18000BDF8
0x18000bd5f  mov     edx, [rdi+60h]
0x18000bd62  cmp     edx, ebp
0x18000bd64  jbe     loc_18000BDF8
0x18000bd6a  mov     ecx, ebp
0x18000bd6c  lea     r9, [rsp+68h+arg_8]; struct IMFSensorProfileInternal **
0x18000bd71  add     rcx, [rdi+58h]; unsigned __int8 *
0x18000bd75  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x18000bd7a  sub     edx, ebp; unsigned int
0x18000bd7c  mov     [rsp+68h+arg_0], 0
0x18000bd84  mov     [rsp+68h+arg_8], 0
0x18000bd8d  call    ?LoadSensorProfile@SensorProfile@@SAJPEAEKPEAKPEAPEAUIMFSensorProfileInternal@@@Z; SensorProfile::LoadSensorProfile(uchar *,ulong,ulong *,IMFSensorProfileInternal * *)
0x18000bd92  mov     esi, eax
0x18000bd94  test    eax, eax
0x18000bd96  js      loc_18000BE96
0x18000bd9c  mov     r13d, [rdi+48h]
0x18000bda0  lea     rcx, [rdi+40h]
0x18000bda4  mov     rsi, [rsp+68h+arg_8]
0x18000bda9  lea     edx, [r13+1]
0x18000bdad  call    ?SetSize@?$CTEntryArray@PEAVSensorDeviceId@@@@QEAAHKK@Z; CTEntryArray<SensorDeviceId *>::SetSize(ulong,ulong)
0x18000bdb2  test    eax, eax
0x18000bdb4  jz      loc_18000BF42
0x18000bdba  mov     rax, [rdi+40h]
0x18000bdbe  mov     [rax+r13*8], rsi
0x18000bdc2  test    rsi, rsi
0x18000bdc5  jz      short loc_18000BDD6
0x18000bdc7  mov     rax, [rsi]
0x18000bdca  mov     rcx, rsi
0x18000bdcd  mov     rax, [rax+8]
0x18000bdd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdd6  add     ebp, [rsp+68h+arg_0]
0x18000bdda  mov     rcx, [rsp+68h+arg_8]
0x18000bddf  test    rcx, rcx
0x18000bde2  jz      short loc_18000BDF0
0x18000bde4  mov     rax, [rcx]
0x18000bde7  mov     rax, [rax+10h]
0x18000bdeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdf0  inc     r14d
0x18000bdf3  jmp     loc_18000BD55
0x18000bdf8  mov     eax, [r15+4]
0x18000bdfc  mov     [rdi+64h], eax
0x18000bdff  xor     esi, esi
0x18000be01  cmp     cs:byte_18008D62D, 8
0x18000be08  jnb     loc_18000BFAA
0x18000be0e  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000be12  call    cs:__imp_LeaveCriticalSection
0x18000be18  mov     rbx, [rsp+68h+arg_10]
0x18000be20  mov     eax, esi
0x18000be22  add     rsp, 30h
0x18000be26  pop     r15
0x18000be28  pop     r14
0x18000be2a  pop     r13
0x18000be2c  pop     r12
0x18000be2e  pop     rdi
0x18000be2f  pop     rsi
0x18000be30  pop     rbp
0x18000be31  retn
0x18000be32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be39  lea     r8, WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids
0x18000be40  mov     eax, [r14]
0x18000be43  mov     edx, 2Bh ; '+'
0x18000be48  mov     [rsp+68h+var_40], eax
0x18000be4c  mov     r9, rdi
0x18000be4f  mov     [rsp+68h+var_48], r15
0x18000be54  mov     rcx, [rcx+0D8h]
0x18000be5b  call    WPP_SF_qqD
0x18000be60  jmp     loc_18000BD06
0x18000be65  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000be6c  jnb     short loc_18000BED6
0x18000be6e  cmp     cs:byte_18008D62D, 1
0x18000be75  jb      short loc_18000BE0E
0x18000be77  mov     edx, 33h ; '3'
0x18000be7c  jmp     loc_18000BFAF
0x18000be81  mov     esi, 0C00D36B6h
0x18000be86  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000be8d  jb      short loc_18000BE6E
0x18000be8f  mov     edx, 2Ch ; ','
0x18000be94  jmp     short loc_18000BEC0
0x18000be96  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000be9d  jnb     loc_18000BF82
0x18000bea3  mov     rcx, [rsp+68h+arg_8]
0x18000bea8  test    rcx, rcx
0x18000beab  jz      short loc_18000BE6E
0x18000bead  mov     rax, [rcx]
0x18000beb0  mov     rax, [rax+10h]
0x18000beb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beb9  jmp     short loc_18000BE6E
0x18000bebb  mov     edx, 2Dh ; '-'
0x18000bec0  mov     dword ptr [rsp+68h+var_48], esi
0x18000bec4  jmp     short loc_18000BEE6
0x18000bec6  mov     esi, 0C00D7170h
0x18000becb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000bed2  jb      short loc_18000BE6E
0x18000bed4  jmp     short loc_18000BEBB
0x18000bed6  mov     edx, 2Eh ; '.'
0x18000bedb  jmp     short loc_18000BEE2
0x18000bedd  mov     edx, 2Fh ; '/'
0x18000bee2  mov     dword ptr [rsp+68h+var_48], eax
0x18000bee6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000beed  lea     r8, WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids
0x18000bef4  mov     r9, rdi
0x18000bef7  mov     rcx, [rcx+10h]
0x18000befb  call    WPP_SF_qD
0x18000bf00  jmp     loc_18000BE6E
0x18000bf05  mov     eax, [r14]
0x18000bf08  sub     eax, ebp
0x18000bf0a  cmp     eax, r8d
0x18000bf0d  jb      loc_18000BD49
0x18000bf13  mov     rdx, [rdi+58h]
0x18000bf17  mov     rcx, [rdi+68h]; pAttributes
0x18000bf1b  add     rdx, rbp; pBuf
0x18000bf1e  call    cs:__imp_MFInitAttributesFromBlob
0x18000bf24  mov     esi, eax
0x18000bf26  test    eax, eax
0x18000bf28  jns     short loc_18000BF39
0x18000bf2a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000bf31  jb      loc_18000BE6E
0x18000bf37  jmp     short loc_18000BEDD
0x18000bf39  add     ebp, [r15+0Ch]
0x18000bf3d  jmp     loc_18000BD49
0x18000bf42  mov     esi, 8007000Eh
0x18000bf47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000bf4e  jb      short loc_18000BF73
0x18000bf50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf57  lea     r8, WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids
0x18000bf5e  mov     edx, 31h ; '1'
0x18000bf63  mov     dword ptr [rsp+68h+var_48], esi
0x18000bf67  mov     r9, rdi
0x18000bf6a  mov     rcx, [rcx+10h]
0x18000bf6e  call    WPP_SF_qD
0x18000bf73  lea     rcx, [rsp+68h+arg_8]
0x18000bf78  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18000bf7d  jmp     loc_18000BE6E
0x18000bf82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf89  lea     r8, WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids
0x18000bf90  mov     edx, 30h ; '0'
0x18000bf95  mov     dword ptr [rsp+68h+var_48], eax
0x18000bf99  mov     r9, rdi
0x18000bf9c  mov     rcx, [rcx+10h]
0x18000bfa0  call    WPP_SF_qD
0x18000bfa5  jmp     loc_18000BEA3
0x18000bfaa  mov     edx, 34h ; '4'
0x18000bfaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfb6  lea     r8, WPP_a82f70f65d0837e49e498dee1aa4cfb4_Traceguids
0x18000bfbd  mov     r9, rdi
0x18000bfc0  mov     dword ptr [rsp+68h+var_48], esi
0x18000bfc4  mov     rcx, [rcx+0D8h]
0x18000bfcb  call    WPP_SF_qD
0x18000bfd0  jmp     loc_18000BE0E
```
