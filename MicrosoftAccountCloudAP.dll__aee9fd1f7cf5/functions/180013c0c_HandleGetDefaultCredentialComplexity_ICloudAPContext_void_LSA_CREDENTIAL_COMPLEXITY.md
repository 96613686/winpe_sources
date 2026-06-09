# HandleGetDefaultCredentialComplexity(ICloudAPContext *,void *,_LSA_CREDENTIAL_COMPLEXITY *)

- ea: `0x180013c0c`
- end: `0x180013ccd`
- name: `?HandleGetDefaultCredentialComplexity@@YAJPEAVICloudAPContext@@PEAXPEAU_LSA_CREDENTIAL_COMPLEXITY@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(struct ICloudAPContext *, void *, struct _LSA_CREDENTIAL_COMPLEXITY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009c60`

## callees

- `0x180008440`
- `0x18000baac`
- `0x180012800`
- `0x180012924`
- `0x180013c0c`

## string_xrefs

- `0x180013c5a`: `onecoreuap\ds\ext\live\identity\cloudapplugin\logon.cpp`
- `0x180013c2e`: `HandleGetDefaultCredentialComplexity`

## pseudocode

```c
__int64 __fastcall HandleGetDefaultCredentialComplexity(
        struct ICloudAPContext *a1,
        void *a2,
        struct _LSA_CREDENTIAL_COMPLEXITY *a3)
{
  __int64 v5; // rdx
  int v6; // r8d
  unsigned int v7; // ebx
  _BYTE v9[8]; // [rsp+20h] [rbp-28h] BYREF
  int *v10; // [rsp+28h] [rbp-20h]
  __int64 v11; // [rsp+30h] [rbp-18h]
  __int64 v12; // [rsp+38h] [rbp-10h]
  int v13; // [rsp+58h] [rbp+10h] BYREF
  int v14; // [rsp+5Ch] [rbp+14h]

  v14 = HIDWORD(a2);
  v13 = 0;
  v10 = &v13;
  v11 = 0;
  v12 = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\logon.cpp",
    "HandleGetDefaultCredentialComplexity",
    (const char *)0x7B4,
    0,
    (const unsigned __int16 *)"HandleGetDefaultCredentialComplexity");
  if ( a3 )
  {
    *(_DWORD *)a3 = 0;
    *((_WORD *)a3 + 2) = 8;
    *((_WORD *)a3 + 3) = 2;
    if ( (int)GetMSAPasswordPolicyFromRegistry(a1, (unsigned __int16 *)a3 + 2, (unsigned __int16 *)a3 + 3) < 0 )
      GetMSAPasswordPolicyFromService(a1, (unsigned __int16 *)a3 + 2, (unsigned __int16 *)a3 + 3);
  }
  else
  {
    v13 = -1073741811;
  }
  v7 = v13;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v9, v5, v6);
  return v7;
}

```

## disassembly

```asm
0x180013c0c  mov     r11, rsp
0x180013c0f  mov     [r11+8], rbx
0x180013c13  mov     [r11+18h], rsi
0x180013c17  mov     [r11+10h], rdx
0x180013c1b  push    rdi
0x180013c1c  sub     rsp, 40h
0x180013c20  mov     rdi, r8
0x180013c23  mov     rsi, rcx
0x180013c26  mov     [rsp+48h+arg_8], 0
0x180013c2e  lea     rdx, aHandlegetdefau; "HandleGetDefaultCredentialComplexity"
0x180013c35  mov     [r11-28h], rdx
0x180013c39  lea     rax, [r11+10h]
0x180013c3d  mov     [r11-20h], rax
0x180013c41  mov     qword ptr [r11-18h], 0
0x180013c49  mov     qword ptr [r11-10h], 0
0x180013c51  xor     r9d, r9d; unsigned int
0x180013c54  mov     r8d, 7B4h; char *
0x180013c5a  lea     rcx, aOnecoreuapDsEx_5; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180013c61  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180013c66  nop
0x180013c67  test    rdi, rdi
0x180013c6a  jnz     short loc_180013C76
0x180013c6c  mov     [rsp+48h+arg_8], 0C000000Dh
0x180013c74  jmp     short loc_180013CAD
0x180013c76  mov     dword ptr [rdi], 0
0x180013c7c  lea     rbx, [rdi+4]
0x180013c80  mov     word ptr [rbx], 8
0x180013c85  mov     word ptr [rdi+6], 2
0x180013c8b  lea     r8, [rdi+6]; unsigned __int16 *
0x180013c8f  mov     rdx, rbx; unsigned __int16 *
0x180013c92  mov     rcx, rsi; struct ICloudAPContext *
0x180013c95  call    ?GetMSAPasswordPolicyFromRegistry@@YAJPEAVICloudAPContext@@PEAG1@Z; GetMSAPasswordPolicyFromRegistry(ICloudAPContext *,ushort *,ushort *)
0x180013c9a  test    eax, eax
0x180013c9c  jns     short loc_180013CAD
0x180013c9e  lea     r8, [rdi+6]; unsigned __int16 *
0x180013ca2  mov     rdx, rbx; unsigned __int16 *
0x180013ca5  mov     rcx, rsi; struct ICloudAPContext *
0x180013ca8  call    ?GetMSAPasswordPolicyFromService@@YAJPEAVICloudAPContext@@PEAG1@Z; GetMSAPasswordPolicyFromService(ICloudAPContext *,ushort *,ushort *)
0x180013cad  mov     ebx, [rsp+48h+arg_8]
0x180013cb1  lea     rcx, [rsp+48h+var_28]
0x180013cb6  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180013cbb  mov     eax, ebx
0x180013cbd  mov     rbx, [rsp+48h+arg_0]
0x180013cc2  mov     rsi, [rsp+48h+arg_10]
0x180013cc7  add     rsp, 40h
0x180013ccb  pop     rdi
0x180013ccc  retn
```
