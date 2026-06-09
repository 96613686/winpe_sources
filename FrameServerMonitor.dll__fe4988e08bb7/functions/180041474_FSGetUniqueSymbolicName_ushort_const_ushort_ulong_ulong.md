# FSGetUniqueSymbolicName(ushort const *,ushort *,ulong,ulong *)

- ea: `0x180041474`
- end: `0x1800416d4`
- name: `?FSGetUniqueSymbolicName@@YAJPEBGPEAGKPEAK@Z`
- size: `608`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `4`
- callee_count: `8`
- tags: `reparse_path`

## callers

- `0x1800115e0`
- `0x180036cb8`
- `0x18003701c`
- `0x18003b9a4`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180004f34`
- `0x1800060f8`
- `0x180006a98`
- `0x18000cadc`
- `0x180041474`
- `0x180041b60`

## import_xrefs

- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x180041555`
- `CFGMGR32!CM_Get_Device_Interface_AliasW` at `0x180041555`

## pseudocode

```c
__int64 __fastcall FSGetUniqueSymbolicName(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r14
  int v8; // ebx
  int i; // ebx
  __int64 v10; // rdx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rax
  unsigned int v13; // eax
  ULONG pulLength[2]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v16[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszAliasDeviceInterface[264]; // [rsp+70h] [rbp-90h] BYREF

  v4 = a3;
  *(_QWORD *)pulLength = 0;
  v16[0] = GUID_e5323777_f976_4f5b_9b55_b94699c46e44;
  v16[1] = GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca;
  v16[2] = GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( !a4 )
        goto LABEL_8;
    }
    else if ( !a4 )
    {
      return (unsigned int)-2147467261;
    }
    *a4 = 0;
LABEL_8:
    for ( i = 0; ; ++i )
    {
      if ( (unsigned __int64)i >= 3 )
      {
        v8 = StringCchLengthW(a1, 0x104u, (unsigned __int64 *)pulLength);
        if ( v8 >= 0 )
        {
          v12 = ++*(_QWORD *)pulLength;
          if ( a4 )
            *a4 = v12;
          if ( a2 && (_DWORD)v4 )
          {
            if ( v4 < v12 )
            {
              return (unsigned int)-1072860816;
            }
            else
            {
              v8 = StringCchCopyW(a2, v4, a1);
              if ( v8 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v10 = 34;
                goto LABEL_16;
              }
            }
          }
          else
          {
            v13 = v8;
            if ( !a4 )
              return (unsigned int)-2147467261;
            return v13;
          }
        }
        else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 33;
          goto LABEL_16;
        }
        return (unsigned int)v8;
      }
      memset_0(pszAliasDeviceInterface, 0, 0x208u);
      *(_QWORD *)pulLength = 260;
      if ( !CM_Get_Device_Interface_AliasW(a1, (LPGUID)&v16[i], pszAliasDeviceInterface, pulLength, 0)
        && FSIsDeviceInterfaceEnabled(pszAliasDeviceInterface) )
      {
        break;
      }
    }
    v8 = StringCchLengthW(pszAliasDeviceInterface, 0x104u, (unsigned __int64 *)pulLength);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        return (unsigned int)v8;
      v10 = 31;
      goto LABEL_16;
    }
    v11 = ++*(_QWORD *)pulLength;
    if ( a4 )
      *a4 = v11;
    if ( a2 && (_DWORD)v4 )
    {
      if ( v4 < v11 )
        return (unsigned int)-1072860816;
      v8 = StringCchCopyW(a2, v4, pszAliasDeviceInterface);
      if ( v8 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v10 = 32;
LABEL_16:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v8);
        return (unsigned int)v8;
      }
      return (unsigned int)v8;
    }
    if ( a4 )
      return (unsigned int)v8;
    return (unsigned int)-2147467261;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x180041474  push    rbp
0x180041476  push    rbx
0x180041477  push    rsi
0x180041478  push    rdi
0x180041479  push    r12
0x18004147b  push    r14
0x18004147d  push    r15
0x18004147f  lea     rbp, [rsp-190h]
0x180041487  sub     rsp, 290h
0x18004148e  mov     rax, cs:__security_cookie
0x180041495  xor     rax, rsp
0x180041498  mov     [rbp+1C0h+var_40], rax
0x18004149f  mov     r14d, r8d
0x1800414a2  mov     rdi, r9
0x1800414a5  mov     qword ptr [rsp+2C0h+pulLength], 0
0x1800414ae  mov     rsi, rdx
0x1800414b1  mov     r12, rcx
0x1800414b4  movups  xmm0, xmmword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data1
0x1800414bb  movups  xmm1, xmmword ptr cs:_GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca.Data1
0x1800414c2  movdqu  [rsp+2C0h+var_288], xmm0
0x1800414c8  movups  xmm0, xmmword ptr cs:_GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8.Data1
0x1800414cf  movdqu  [rsp+2C0h+var_278], xmm1
0x1800414d5  movdqu  [rsp+2C0h+var_268], xmm0
0x1800414db  test    rcx, rcx
0x1800414de  jnz     short loc_1800414EA
0x1800414e0  mov     ebx, 80070057h
0x1800414e5  jmp     loc_1800416B1
0x1800414ea  test    rsi, rsi
0x1800414ed  jnz     short loc_1800414FE
0x1800414ef  test    rdi, rdi
0x1800414f2  jnz     short loc_180041503
0x1800414f4  mov     ebx, 80004003h
0x1800414f9  jmp     loc_1800416B1
0x1800414fe  test    rdi, rdi
0x180041501  jz      short loc_18004150A
0x180041503  mov     dword ptr [r9], 0
0x18004150a  xor     ebx, ebx
0x18004150c  movsxd  r15, ebx
0x18004150f  cmp     r15, 3
0x180041513  jnb     loc_180041629
0x180041519  xor     edx, edx; Val
0x18004151b  lea     rcx, [rsp+2C0h+pszAliasDeviceInterface]; void *
0x180041520  mov     r8d, 208h; Size
0x180041526  call    memset_0
0x18004152b  lea     rdx, [rsp+2C0h+var_288]
0x180041530  shl     r15, 4
0x180041534  add     rdx, r15; AliasInterfaceGuid
0x180041537  mov     qword ptr [rsp+2C0h+pulLength], 104h
0x180041540  lea     r9, [rsp+2C0h+pulLength]; pulLength
0x180041545  mov     [rsp+2C0h+ulFlags], 0; ulFlags
0x18004154d  lea     r8, [rsp+2C0h+pszAliasDeviceInterface]; pszAliasDeviceInterface
0x180041552  mov     rcx, r12; pszDeviceInterface
0x180041555  call    cs:__imp_CM_Get_Device_Interface_AliasW
0x18004155b  test    eax, eax
0x18004155d  jnz     short loc_18004156D
0x18004155f  lea     rcx, [rsp+2C0h+pszAliasDeviceInterface]; unsigned __int16 *
0x180041564  call    ?FSIsDeviceInterfaceEnabled@@YA_NPEBG@Z; FSIsDeviceInterfaceEnabled(ushort const *)
0x180041569  test    al, al
0x18004156b  jnz     short loc_180041571
0x18004156d  inc     ebx
0x18004156f  jmp     short loc_18004150C
0x180041571  lea     r8, [rsp+2C0h+pulLength]; unsigned __int64 *
0x180041576  mov     edx, 104h; unsigned __int64
0x18004157b  lea     rcx, [rsp+2C0h+pszAliasDeviceInterface]; unsigned __int16 *
0x180041580  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180041585  mov     ebx, eax
0x180041587  test    eax, eax
0x180041589  jns     short loc_1800415C0
0x18004158b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041590  cmp     al, 1
0x180041592  jb      loc_1800416B1
0x180041598  mov     edx, 1Fh
0x18004159d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800415a4  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x1800415ab  xor     r9d, r9d
0x1800415ae  mov     [rsp+2C0h+ulFlags], ebx
0x1800415b2  mov     rcx, [rcx+10h]
0x1800415b6  call    WPP_SF_qD
0x1800415bb  jmp     loc_1800416B1
0x1800415c0  mov     rax, qword ptr [rsp+2C0h+pulLength]
0x1800415c5  inc     rax
0x1800415c8  mov     qword ptr [rsp+2C0h+pulLength], rax
0x1800415cd  test    rdi, rdi
0x1800415d0  jz      short loc_1800415D4
0x1800415d2  mov     [rdi], eax
0x1800415d4  test    rsi, rsi
0x1800415d7  jz      short loc_18004161B
0x1800415d9  test    r14d, r14d
0x1800415dc  jz      short loc_18004161B
0x1800415de  mov     rdx, r14; unsigned __int64
0x1800415e1  cmp     r14, rax
0x1800415e4  jnb     short loc_1800415F0
0x1800415e6  mov     ebx, 0C00D7170h
0x1800415eb  jmp     loc_1800416B1
0x1800415f0  lea     r8, [rsp+2C0h+pszAliasDeviceInterface]; unsigned __int16 *
0x1800415f5  mov     rcx, rsi; unsigned __int16 *
0x1800415f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800415fd  mov     ebx, eax
0x1800415ff  test    eax, eax
0x180041601  jns     loc_1800416B1
0x180041607  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004160c  cmp     al, 1
0x18004160e  jb      loc_1800416B1
0x180041614  mov     edx, 20h ; ' '
0x180041619  jmp     short loc_18004159D
0x18004161b  test    rdi, rdi
0x18004161e  jnz     loc_1800416B1
0x180041624  jmp     loc_1800414F4
0x180041629  lea     r8, [rsp+2C0h+pulLength]; unsigned __int64 *
0x18004162e  mov     edx, 104h; unsigned __int64
0x180041633  mov     rcx, r12; unsigned __int16 *
0x180041636  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004163b  mov     ebx, eax
0x18004163d  test    eax, eax
0x18004163f  jns     short loc_180041654
0x180041641  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041646  cmp     al, 1
0x180041648  jb      short loc_1800416B1
0x18004164a  mov     edx, 21h ; '!'
0x18004164f  jmp     loc_18004159D
0x180041654  mov     rax, qword ptr [rsp+2C0h+pulLength]
0x180041659  inc     rax
0x18004165c  mov     qword ptr [rsp+2C0h+pulLength], rax
0x180041661  test    rdi, rdi
0x180041664  jz      short loc_180041668
0x180041666  mov     [rdi], eax
0x180041668  test    rsi, rsi
0x18004166b  jz      short loc_1800416A2
0x18004166d  test    r14d, r14d
0x180041670  jz      short loc_1800416A2
0x180041672  mov     rdx, r14; unsigned __int64
0x180041675  cmp     r14, rax
0x180041678  jb      loc_1800415E6
0x18004167e  mov     r8, r12; unsigned __int16 *
0x180041681  mov     rcx, rsi; unsigned __int16 *
0x180041684  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041689  mov     ebx, eax
0x18004168b  test    eax, eax
0x18004168d  jns     short loc_1800416B1
0x18004168f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041694  cmp     al, 1
0x180041696  jb      short loc_1800416B1
0x180041698  mov     edx, 22h ; '"'
0x18004169d  jmp     loc_18004159D
0x1800416a2  mov     eax, ebx
0x1800416a4  test    rdi, rdi
0x1800416a7  mov     ebx, 80004003h
0x1800416ac  cmovz   eax, ebx
0x1800416af  mov     ebx, eax
0x1800416b1  mov     eax, ebx
0x1800416b3  mov     rcx, [rbp+1C0h+var_40]
0x1800416ba  xor     rcx, rsp; StackCookie
0x1800416bd  call    __security_check_cookie
0x1800416c2  add     rsp, 290h
0x1800416c9  pop     r15
0x1800416cb  pop     r14
0x1800416cd  pop     r12
0x1800416cf  pop     rdi
0x1800416d0  pop     rsi
0x1800416d1  pop     rbx
0x1800416d2  pop     rbp
0x1800416d3  retn
```
