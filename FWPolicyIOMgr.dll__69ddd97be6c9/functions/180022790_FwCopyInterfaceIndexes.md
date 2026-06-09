# FwCopyInterfaceIndexes

- ea: `0x180022790`
- end: `0x180022833`
- name: `FwCopyInterfaceIndexes`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800042c4`
- `0x18001e9ac`
- `0x180022790`

## import_xrefs

- `fwbase!FwFree` at `0x180022812`
- `fwbase!FwFree` at `0x180022812`
- `fwbase!FwArrayCopy` at `0x1800227cc`
- `fwbase!FwArrayCopy` at `0x1800227cc`

## pseudocode

```c
__int64 __fastcall FwCopyInterfaceIndexes(__int64 a1, __int64 a2)
{
  int v4; // edi
  __int64 v5; // rcx

  if ( *(_DWORD *)a2 || *(_QWORD *)(a2 + 8) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v4 = FwArrayCopy(
         8,
         FwCopyIPv4SubNet,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         a1,
         a2);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
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
0x180022790  mov     [rsp+arg_0], rbx
0x180022795  push    rdi
0x180022796  sub     rsp, 30h
0x18002279a  cmp     dword ptr [rdx], 0
0x18002279d  mov     rbx, rdx
0x1800227a0  mov     rdi, rcx
0x1800227a3  jnz     short loc_1800227AC
0x1800227a5  cmp     qword ptr [rdx+8], 0
0x1800227aa  jz      short loc_1800227B1
0x1800227ac  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800227b1  mov     r9, rdi
0x1800227b4  mov     [rsp+38h+var_18], rbx
0x1800227b9  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800227c0  mov     ecx, 8
0x1800227c5  lea     rdx, FwCopyIPv4SubNet
0x1800227cc  call    cs:__imp_FwArrayCopy
0x1800227d2  mov     edi, eax
0x1800227d4  test    eax, eax
0x1800227d6  jns     short loc_180022826
0x1800227d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800227df  lea     rax, WPP_GLOBAL_Control
0x1800227e6  cmp     rcx, rax
0x1800227e9  jz      short loc_180022809
0x1800227eb  test    byte ptr [rcx+1Ch], 1
0x1800227ef  jz      short loc_180022809
0x1800227f1  mov     rcx, [rcx+10h]
0x1800227f5  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x1800227fc  mov     edx, 19h
0x180022801  mov     r9d, edi
0x180022804  call    WPP_SF_d
0x180022809  mov     rcx, [rbx+8]
0x18002280d  test    rcx, rcx
0x180022810  jz      short loc_180022818
0x180022812  call    cs:__imp_FwFree
0x180022818  mov     qword ptr [rbx+8], 0
0x180022820  mov     dword ptr [rbx], 0
0x180022826  mov     rbx, [rsp+38h+arg_0]
0x18002282b  mov     eax, edi
0x18002282d  add     rsp, 30h
0x180022831  pop     rdi
0x180022832  retn
```
