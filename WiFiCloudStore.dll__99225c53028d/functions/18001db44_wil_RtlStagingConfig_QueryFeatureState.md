# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18001db44`
- end: `0x18001dc69`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001da60`

## callees

- `0x180010864`
- `0x18001db44`
- `0x18002a030`
- `0x180041010`

## string_xrefs

- `0x18001db90`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v9; // r8d
  unsigned int v10; // r9d
  int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // ecx
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+38h] [rbp-30h] BYREF
  int v17; // [rsp+40h] [rbp-28h]

  v15 = 0;
  v7 = a3 == 0;
  v16 = 0;
  v17 = 0;
  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v9 = -1073741511;
LABEL_4:
      v10 = 0;
      goto LABEL_5;
    }
  }
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v7, &v15, &v16);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_4;
    v10 = 1;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v16) >> 7) & 1;
  }
  else
  {
    v13 = HIDWORD(v16);
    v10 = 1;
    v14 = HIDWORD(v16);
    *(_DWORD *)(a1 + 12) = v17;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v14 >> 14;
    *(_DWORD *)a1 = (v14 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v13) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v13 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v13 >> 6) & 1;
  }
LABEL_5:
  if ( a4 )
    *a4 = v9 != -2147483614;
  return v10;
}

```

## disassembly

```asm
0x18001db44  mov     [rsp+arg_10], rbx
0x18001db49  push    rbp
0x18001db4a  push    rsi
0x18001db4b  push    rdi
0x18001db4c  sub     rsp, 50h
0x18001db50  mov     rax, cs:__security_cookie
0x18001db57  xor     rax, rsp
0x18001db5a  mov     [rsp+68h+var_20], rax
0x18001db5f  xor     esi, esi
0x18001db61  mov     [rsp+68h+var_38], 0
0x18001db6a  test    r8d, r8d
0x18001db6d  mov     rdi, r9
0x18001db70  mov     ebp, edx
0x18001db72  mov     rbx, rcx
0x18001db75  setz    sil
0x18001db79  xor     eax, eax
0x18001db7b  mov     [rsp+68h+var_30], rax
0x18001db80  mov     [rsp+68h+var_28], eax
0x18001db84  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001db8b  test    rax, rax
0x18001db8e  jnz     short loc_18001DBE4
0x18001db90  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001db97  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001db9c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001dba3  test    rax, rax
0x18001dba6  jnz     short loc_18001DBE4
0x18001dba8  mov     r8d, 0C0000139h
0x18001dbae  xor     r9d, r9d
0x18001dbb1  test    rdi, rdi
0x18001dbb4  jz      short loc_18001DBC4
0x18001dbb6  xor     ecx, ecx
0x18001dbb8  cmp     r8d, 80000022h
0x18001dbbf  setnz   cl
0x18001dbc2  mov     [rdi], ecx
0x18001dbc4  mov     eax, r9d
0x18001dbc7  mov     rcx, [rsp+68h+var_20]
0x18001dbcc  xor     rcx, rsp; StackCookie
0x18001dbcf  call    __security_check_cookie
0x18001dbd4  mov     rbx, [rsp+68h+arg_10]
0x18001dbdc  add     rsp, 50h
0x18001dbe0  pop     rdi
0x18001dbe1  pop     rsi
0x18001dbe2  pop     rbp
0x18001dbe3  retn
0x18001dbe4  lea     r9, [rsp+68h+var_30]
0x18001dbe9  mov     edx, esi
0x18001dbeb  lea     r8, [rsp+68h+var_38]
0x18001dbf0  mov     ecx, ebp
0x18001dbf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbf7  mov     r8d, eax
0x18001dbfa  test    eax, eax
0x18001dbfc  jnz     short loc_18001DC46
0x18001dbfe  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001dc02  lea     r9d, [r8+1]
0x18001dc06  mov     eax, [rsp+68h+var_28]
0x18001dc0a  mov     ecx, edx
0x18001dc0c  mov     [rbx+0Ch], eax
0x18001dc0f  mov     eax, edx
0x18001dc11  shr     eax, 0Eh
0x18001dc14  shr     ecx, 4
0x18001dc17  and     eax, 3
0x18001dc1a  and     ecx, 3
0x18001dc1d  mov     [rbx+8], eax
0x18001dc20  mov     [rbx], ecx
0x18001dc22  mov     eax, edx
0x18001dc24  mov     ecx, edx
0x18001dc26  shr     eax, 6
0x18001dc29  shr     ecx, 8
0x18001dc2c  and     eax, r9d
0x18001dc2f  and     cl, 3Fh
0x18001dc32  shr     edx, 7
0x18001dc35  and     edx, r9d
0x18001dc38  mov     [rbx+4], cl
0x18001dc3b  mov     [rbx+10h], edx
0x18001dc3e  mov     [rbx+14h], eax
0x18001dc41  jmp     loc_18001DBB1
0x18001dc46  cmp     eax, 117h
0x18001dc4b  jnz     loc_18001DBAE
0x18001dc51  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18001dc55  mov     r9d, 1
0x18001dc5b  shr     eax, 7
0x18001dc5e  and     eax, r9d
0x18001dc61  mov     [rbx+10h], eax
0x18001dc64  jmp     loc_18001DBB1
```
