# FwCopyInterfaceLuids

- ea: `0x180022840`
- end: `0x1800228e3`
- name: `FwCopyInterfaceLuids`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800042c4`
- `0x18001e9ac`
- `0x180022840`

## import_xrefs

- `fwbase!FwFree` at `0x1800228c2`
- `fwbase!FwFree` at `0x1800228c2`
- `fwbase!FwArrayCopy` at `0x18002287c`
- `fwbase!FwArrayCopy` at `0x18002287c`

## pseudocode

```c
__int64 __fastcall FwCopyInterfaceLuids(__int64 a1, __int64 a2)
{
  int v4; // edi
  __int64 v5; // rcx

  if ( *(_DWORD *)a2 || *(_QWORD *)(a2 + 8) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v4 = FwArrayCopy(
         16,
         FwShallowCopySidAndAttributes,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         a1,
         a2);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids,
        (unsigned int)v4);
    v5 = *(_QWORD *)(a2 + 8);
    if ( v5 )
      FwFree(v5);
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)a2 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180022840  mov     [rsp+arg_0], rbx
0x180022845  push    rdi
0x180022846  sub     rsp, 30h
0x18002284a  cmp     dword ptr [rdx], 0
0x18002284d  mov     rbx, rdx
0x180022850  mov     rdi, rcx
0x180022853  jnz     short loc_18002285C
0x180022855  cmp     qword ptr [rdx+8], 0
0x18002285a  jz      short loc_180022861
0x18002285c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180022861  mov     r9, rdi
0x180022864  mov     [rsp+38h+var_18], rbx
0x180022869  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180022870  mov     ecx, 10h
0x180022875  lea     rdx, ?FwShallowCopySidAndAttributes@@YAJPEBXPEAX@Z; FwShallowCopySidAndAttributes(void const *,void *)
0x18002287c  call    cs:__imp_FwArrayCopy
0x180022882  mov     edi, eax
0x180022884  test    eax, eax
0x180022886  jns     short loc_1800228D6
0x180022888  mov     rcx, cs:WPP_GLOBAL_Control
0x18002288f  lea     rax, WPP_GLOBAL_Control
0x180022896  cmp     rcx, rax
0x180022899  jz      short loc_1800228B9
0x18002289b  test    byte ptr [rcx+1Ch], 1
0x18002289f  jz      short loc_1800228B9
0x1800228a1  mov     rcx, [rcx+10h]
0x1800228a5  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x1800228ac  mov     edx, 17h
0x1800228b1  mov     r9d, edi
0x1800228b4  call    WPP_SF_d
0x1800228b9  mov     rcx, [rbx+8]
0x1800228bd  test    rcx, rcx
0x1800228c0  jz      short loc_1800228C8
0x1800228c2  call    cs:__imp_FwFree
0x1800228c8  mov     qword ptr [rbx+8], 0
0x1800228d0  mov     dword ptr [rbx], 0
0x1800228d6  mov     rbx, [rsp+38h+arg_0]
0x1800228db  mov     eax, edi
0x1800228dd  add     rsp, 30h
0x1800228e1  pop     rdi
0x1800228e2  retn
```
