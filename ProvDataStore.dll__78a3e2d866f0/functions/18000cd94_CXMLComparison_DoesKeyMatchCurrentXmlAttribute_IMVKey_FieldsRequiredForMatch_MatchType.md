# CXMLComparison::DoesKeyMatchCurrentXmlAttribute(IMVKey *,FieldsRequiredForMatch,MatchType *)

- ea: `0x18000cd94`
- end: `0x18000cf16`
- name: `?DoesKeyMatchCurrentXmlAttribute@CXMLComparison@@QEAAJPEAUIMVKey@@W4FieldsRequiredForMatch@@PEAW4MatchType@@@Z`
- size: `386`
- prototype: `__int64 __fastcall(__int64, __int64 *, char, _DWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cf20`
- `0x18000d150`
- `0x18000f2fc`

## callees

- `0x180005644`
- `0x18000cd94`
- `0x180012010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ce0d`
- `msvcrt!_wcsicmp` at `0x18000ce7d`
- `msvcrt!_wcsicmp` at `0x18000ce99`
- `msvcrt!_wcsicmp` at `0x18000ceb5`
- `msvcrt!_wcsicmp` at `0x18000ced1`
- `msvcrt!_wcsicmp` at `0x18000ceed`
- `msvcrt!_wcsicmp` at `0x18000ce0d`
- `msvcrt!_wcsicmp` at `0x18000ce7d`
- `msvcrt!_wcsicmp` at `0x18000ce99`
- `msvcrt!_wcsicmp` at `0x18000ceb5`
- `msvcrt!_wcsicmp` at `0x18000ced1`
- `msvcrt!_wcsicmp` at `0x18000ceed`

## string_xrefs

- `0x18000cde4`: `onecoreuap\admin\prov\multivariant\datastore\src\sourcedatastoreparse.cpp`

## pseudocode

```c
__int64 __fastcall CXMLComparison::DoesKeyMatchCurrentXmlAttribute(__int64 a1, __int64 *a2, char a3, _DWORD *a4)
{
  int v8; // esi
  __int64 v9; // rdx
  const wchar_t *v11; // rdx
  __int64 v12; // rax
  _QWORD *v13; // rdx
  bool v14; // cf
  wchar_t *String1; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v17; // [rsp+60h] [rbp+18h] BYREF

  String1 = 0;
  if ( (a3 & 1) == 0 )
    goto LABEL_14;
  v8 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(*a2 + 40))(a2, &String1);
  if ( v8 < 0 )
  {
    v9 = 475;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\sourcedatastoreparse.cpp",
      (const char *)(unsigned int)v8,
      (int)String1);
    return (unsigned int)v8;
  }
  v11 = (const wchar_t *)(a1 + 16);
  if ( *(_QWORD *)(a1 + 40) >= 8u )
    v11 = *(const wchar_t **)v11;
  if ( _wcsicmp(String1, v11) )
  {
    *a4 = 1;
  }
  else
  {
LABEL_14:
    if ( (a3 & 2) == 0 )
      goto LABEL_30;
    v12 = *a2;
    v13 = (_QWORD *)(a1 + 48);
    v14 = *(_QWORD *)(a1 + 72) < 8u;
    v17 = 0;
    if ( !v14 )
      v13 = (_QWORD *)*v13;
    v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, int *))(v12 + 56))(a2, v13, &v17);
    if ( v8 < 0 )
    {
      v9 = 488;
      goto LABEL_4;
    }
    if ( v17 )
    {
LABEL_30:
      if ( _wcsicmp(L"mcc", String1) )
      {
        if ( _wcsicmp(L"mnc", String1) )
        {
          if ( _wcsicmp(L"roaming", String1) )
          {
            if ( _wcsicmp(L"Imsi", String1) )
            {
              if ( !_wcsicmp(L"Esim_Prov", String1) )
                *(_DWORD *)(a1 + 84) |= 0x20u;
            }
            else
            {
              *(_DWORD *)(a1 + 84) |= 0x10u;
            }
          }
          else
          {
            *(_DWORD *)(a1 + 84) |= 4u;
          }
        }
        else
        {
          *(_DWORD *)(a1 + 84) |= 2u;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 84) |= 1u;
      }
      *a4 = 3;
    }
    else
    {
      *a4 = 2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000cd94  mov     r11, rsp
0x18000cd97  mov     [r11+8], rbx
0x18000cd9b  mov     [r11+10h], rbp
0x18000cd9f  push    rsi
0x18000cda0  push    rdi
0x18000cda1  push    r14
0x18000cda3  sub     rsp, 30h
0x18000cda7  mov     qword ptr [r11-28h], 0
0x18000cdaf  mov     rdi, r9
0x18000cdb2  mov     ebp, r8d
0x18000cdb5  mov     r14, rdx
0x18000cdb8  mov     rbx, rcx
0x18000cdbb  test    r8b, 1
0x18000cdbf  jz      short loc_18000CE22
0x18000cdc1  mov     rax, [rdx]
0x18000cdc4  mov     rcx, r14
0x18000cdc7  lea     rdx, [r11-28h]
0x18000cdcb  mov     rax, [rax+28h]
0x18000cdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd4  mov     esi, eax
0x18000cdd6  test    eax, eax
0x18000cdd8  jns     short loc_18000CDFA
0x18000cdda  mov     edx, 1DBh; void *
0x18000cddf  mov     rcx, [rsp+48h]; this
0x18000cde4  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000cdeb  mov     r9d, esi; char *
0x18000cdee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cdf3  mov     eax, esi
0x18000cdf5  jmp     loc_18000CF03
0x18000cdfa  lea     rdx, [rbx+10h]
0x18000cdfe  cmp     qword ptr [rdx+18h], 8
0x18000ce03  jb      short loc_18000CE08
0x18000ce05  mov     rdx, [rdx]; String2
0x18000ce08  mov     rcx, [rsp+48h+String1]; String1
0x18000ce0d  call    cs:__imp__wcsicmp
0x18000ce13  test    eax, eax
0x18000ce15  jz      short loc_18000CE22
0x18000ce17  mov     dword ptr [rdi], 1
0x18000ce1d  jmp     loc_18000CF01
0x18000ce22  test    bpl, 2
0x18000ce26  jz      short loc_18000CE71
0x18000ce28  mov     rax, [r14]
0x18000ce2b  lea     rdx, [rbx+30h]
0x18000ce2f  cmp     qword ptr [rdx+18h], 8
0x18000ce34  mov     [rsp+48h+arg_10], 0
0x18000ce3c  jb      short loc_18000CE41
0x18000ce3e  mov     rdx, [rdx]
0x18000ce41  mov     rax, [rax+38h]
0x18000ce45  lea     r8, [rsp+48h+arg_10]
0x18000ce4a  mov     rcx, r14
0x18000ce4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce52  mov     esi, eax
0x18000ce54  test    eax, eax
0x18000ce56  jns     short loc_18000CE5F
0x18000ce58  mov     edx, 1E8h
0x18000ce5d  jmp     short loc_18000CDDF
0x18000ce5f  cmp     [rsp+48h+arg_10], 0
0x18000ce64  jnz     short loc_18000CE71
0x18000ce66  mov     dword ptr [rdi], 2
0x18000ce6c  jmp     loc_18000CF01
0x18000ce71  mov     rdx, [rsp+48h+String1]; String2
0x18000ce76  lea     rcx, ?gc_wszMCC@@3QBGB; "mcc"
0x18000ce7d  call    cs:__imp__wcsicmp
0x18000ce83  test    eax, eax
0x18000ce85  jnz     short loc_18000CE8D
0x18000ce87  or      dword ptr [rbx+54h], 1
0x18000ce8b  jmp     short loc_18000CEFB
0x18000ce8d  mov     rdx, [rsp+48h+String1]; String2
0x18000ce92  lea     rcx, ?gc_wszMNC@@3QBGB; "mnc"
0x18000ce99  call    cs:__imp__wcsicmp
0x18000ce9f  test    eax, eax
0x18000cea1  jnz     short loc_18000CEA9
0x18000cea3  or      dword ptr [rbx+54h], 2
0x18000cea7  jmp     short loc_18000CEFB
0x18000cea9  mov     rdx, [rsp+48h+String1]; String2
0x18000ceae  lea     rcx, ?gc_wszRoaming@@3QBGB; "roaming"
0x18000ceb5  call    cs:__imp__wcsicmp
0x18000cebb  test    eax, eax
0x18000cebd  jnz     short loc_18000CEC5
0x18000cebf  or      dword ptr [rbx+54h], 4
0x18000cec3  jmp     short loc_18000CEFB
0x18000cec5  mov     rdx, [rsp+48h+String1]; String2
0x18000ceca  lea     rcx, ?gc_wszImsi@@3QBGB; "Imsi"
0x18000ced1  call    cs:__imp__wcsicmp
0x18000ced7  test    eax, eax
0x18000ced9  jnz     short loc_18000CEE1
0x18000cedb  or      dword ptr [rbx+54h], 10h
0x18000cedf  jmp     short loc_18000CEFB
0x18000cee1  mov     rdx, [rsp+48h+String1]; String2
0x18000cee6  lea     rcx, ?gc_wszEsimProv@@3QBGB; "Esim_Prov"
0x18000ceed  call    cs:__imp__wcsicmp
0x18000cef3  test    eax, eax
0x18000cef5  jnz     short loc_18000CEFB
0x18000cef7  or      dword ptr [rbx+54h], 20h
0x18000cefb  mov     dword ptr [rdi], 3
0x18000cf01  xor     eax, eax
0x18000cf03  mov     rbx, [rsp+48h+arg_0]
0x18000cf08  mov     rbp, [rsp+48h+arg_8]
0x18000cf0d  add     rsp, 30h
0x18000cf11  pop     r14
0x18000cf13  pop     rdi
0x18000cf14  pop     rsi
0x18000cf15  retn
```
