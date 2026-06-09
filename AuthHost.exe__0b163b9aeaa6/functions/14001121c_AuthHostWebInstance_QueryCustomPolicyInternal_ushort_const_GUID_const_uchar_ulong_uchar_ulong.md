# AuthHostWebInstance::QueryCustomPolicyInternal(ushort const *,_GUID const &,uchar * *,ulong *,uchar *,ulong)

- ea: `0x14001121c`
- end: `0x14001139a`
- name: `?QueryCustomPolicyInternal@AuthHostWebInstance@@AEAAJPEBGAEBU_GUID@@PEAPEAEPEAKPEAEK@Z`
- size: `382`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, const unsigned __int16 *, const struct _GUID *, unsigned __int8 **, unsigned int *, IID *rclsid, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140011180`

## callees

- `0x14001121c`
- `0x140011438`
- `0x140011550`
- `0x140011610`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140011294`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140011294`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400112a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011339`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400112a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011339`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140011343`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400112d1`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1400112d1`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::QueryCustomPolicyInternal(
        AuthHostWebInstance *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        unsigned __int8 **a4,
        unsigned int *a5,
        IID *rclsid,
        unsigned int a7)
{
  __int64 v8; // rax
  const IID *v10; // rbx
  unsigned int *v11; // r14
  unsigned __int8 *v12; // rax
  int v14; // ebp
  int v15; // r8d
  unsigned int v16; // esi
  PVOID v17; // rcx
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  pv = this;
  v8 = *(_QWORD *)&a3->Data1 - 0x11D0FA3810200490LL;
  if ( *(_QWORD *)&a3->Data1 == 0x11D0FA3810200490LL )
    v8 = *(_QWORD *)a3->Data4 + 0x3F00F0365FFFF154LL;
  if ( v8 )
  {
    v16 = -2146697199;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF__guid_S(*((_QWORD *)WPP_GLOBAL_Control + 7), (_DWORD)a2, (_DWORD)a3, (_DWORD)a3, (__int64)a2);
    }
  }
  else
  {
    pv = 0;
    if ( a7 != 32 || (v10 = rclsid) == 0 || !a4 || (v11 = a5) == 0 )
    {
      CoTaskMemFree(0);
      return 2147942487LL;
    }
    v12 = (unsigned __int8 *)CoTaskMemAlloc(4u);
    *a4 = v12;
    if ( !v12 )
    {
      CoTaskMemFree(pv);
      return 2147942414LL;
    }
    *v11 = 4;
    v14 = 0;
    *(_DWORD *)*a4 = 3;
    if ( StringFromCLSID(v10, (LPOLESTR *)&pv) >= 0 )
      v14 = (int)pv;
    v16 = 0;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
    {
      WPP_SF_S_guid_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, v15, v14, (__int64)v10, (__int64)a2);
    }
    if ( (Microsoft_Windows_WebAuthEnableBits & 4) != 0 )
      McTemplateU0jz_EventWriteTransfer(v17, CustomConfirmObjectSafetyDisallowedEvent, v10, a2);
    CoTaskMemFree(pv);
  }
  return v16;
}

```

## disassembly

```asm
0x14001121c  mov     [rsp+arg_8], rbx
0x140011221  mov     [rsp+arg_10], rbp
0x140011226  mov     [rsp+pv], rcx
0x14001122b  push    rsi
0x14001122c  push    rdi
0x14001122d  push    r14
0x14001122f  sub     rsp, 30h
0x140011233  mov     rax, [r8]
0x140011236  mov     rsi, r9
0x140011239  sub     rax, cs:qword_140018780
0x140011240  mov     rdi, rdx
0x140011243  jnz     short loc_140011250
0x140011245  mov     rax, [r8+8]
0x140011249  sub     rax, cs:qword_140018788
0x140011250  test    rax, rax
0x140011253  jnz     loc_140011350
0x140011259  cmp     [rsp+48h+arg_30], 20h ; ' '
0x140011261  mov     [rsp+48h+pv], rax
0x140011266  jnz     loc_140011341
0x14001126c  mov     rbx, [rsp+48h+rclsid]
0x140011271  test    rbx, rbx
0x140011274  jz      loc_140011341
0x14001127a  test    rsi, rsi
0x14001127d  jz      loc_140011341
0x140011283  mov     r14, [rsp+48h+arg_20]
0x140011288  test    r14, r14
0x14001128b  jz      loc_140011341
0x140011291  lea     ecx, [rax+4]; cb
0x140011294  call    cs:__imp_CoTaskMemAlloc
0x14001129a  mov     [rsi], rax
0x14001129d  test    rax, rax
0x1400112a0  jnz     short loc_1400112B7
0x1400112a2  mov     rcx, [rsp+48h+pv]; pv
0x1400112a7  call    cs:__imp_CoTaskMemFree
0x1400112ad  mov     eax, 8007000Eh
0x1400112b2  jmp     loc_140011387
0x1400112b7  mov     dword ptr [r14], 4
0x1400112be  lea     rdx, [rsp+48h+pv]; lplpsz
0x1400112c3  mov     rax, [rsi]
0x1400112c6  mov     rcx, rbx; rclsid
0x1400112c9  xor     ebp, ebp
0x1400112cb  mov     dword ptr [rax], 3
0x1400112d1  call    cs:__imp_StringFromCLSID
0x1400112d7  test    eax, eax
0x1400112d9  cmovns  rbp, [rsp+48h+pv]
0x1400112df  xor     esi, esi
0x1400112e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400112e8  lea     rax, WPP_GLOBAL_Control
0x1400112ef  cmp     rcx, rax
0x1400112f2  jz      short loc_140011319
0x1400112f4  test    byte ptr [rcx+44h], 20h
0x1400112f8  jz      short loc_140011319
0x1400112fa  cmp     byte ptr [rcx+41h], 3
0x1400112fe  jb      short loc_140011319
0x140011300  mov     rcx, [rcx+38h]
0x140011304  lea     edx, [rsi+0Ch]
0x140011307  mov     [rsp+48h+var_20], rdi
0x14001130c  mov     r9, rbp
0x14001130f  mov     [rsp+48h+var_28], rbx
0x140011314  call    WPP_SF_S_guid_S
0x140011319  test    cs:Microsoft_Windows_WebAuthEnableBits, 4
0x140011320  jz      short loc_140011334
0x140011322  mov     r9, rdi
0x140011325  lea     rdx, CustomConfirmObjectSafetyDisallowedEvent
0x14001132c  mov     r8, rbx
0x14001132f  call    McTemplateU0jz_EventWriteTransfer
0x140011334  mov     rcx, [rsp+48h+pv]; pv
0x140011339  call    cs:__imp_CoTaskMemFree
0x14001133f  jmp     short loc_140011385
0x140011341  xor     ecx, ecx; pv
0x140011343  call    cs:__imp_CoTaskMemFree
0x140011349  mov     eax, 80070057h
0x14001134e  jmp     short loc_140011387
0x140011350  mov     rcx, cs:WPP_GLOBAL_Control
0x140011357  lea     rax, WPP_GLOBAL_Control
0x14001135e  mov     esi, 800C0011h
0x140011363  cmp     rcx, rax
0x140011366  jz      short loc_140011385
0x140011368  test    byte ptr [rcx+44h], 20h
0x14001136c  jz      short loc_140011385
0x14001136e  cmp     byte ptr [rcx+41h], 4
0x140011372  jb      short loc_140011385
0x140011374  mov     rcx, [rcx+38h]
0x140011378  mov     r9, r8
0x14001137b  mov     [rsp+48h+var_28], rdi
0x140011380  call    WPP_SF__guid_S
0x140011385  mov     eax, esi
0x140011387  mov     rbx, [rsp+48h+arg_8]
0x14001138c  mov     rbp, [rsp+48h+arg_10]
0x140011391  add     rsp, 30h
0x140011395  pop     r14
0x140011397  pop     rdi
0x140011398  pop     rsi
0x140011399  retn
```
