# QueryServiceStartType

- ea: `0x180052480`
- end: `0x18005261a`
- name: `QueryServiceStartType`
- size: `410`
- prototype: `__int64 __fastcall(SC_HANDLE hService)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800521a0`

## callees

- `0x1800074a0`
- `0x18000a430`
- `0x18001dee8`
- `0x18005097c`
- `0x180052480`
- `0x180052620`
- `0x180065035`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005250e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005257a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800524c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005250e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005257a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800524c2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180052570`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x1800524c2`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x180052570`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall QueryServiceStartType(SC_HANDLE hService, _QWORD *a2)
{
  signed int LastError; // eax
  LPQUERY_SERVICE_CONFIGW v5; // rdi
  signed int v6; // edi
  DWORD dwStartType; // ebx
  LPQUERY_SERVICE_CONFIGW lpServiceConfig_8[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-C0h]
  __int64 v11; // [rsp+50h] [rbp-B8h]
  _BYTE pExceptionObject[208]; // [rsp+58h] [rbp-B0h] BYREF
  DWORD pcbBytesNeeded; // [rsp+128h] [rbp+20h] BYREF

  v11 = -2;
  pcbBytesNeeded = 0;
  QueryServiceConfigW(hService, 0, 0, &pcbBytesNeeded);
  if ( GetLastError() != 122 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( a2[3] >= 8u )
        a2 = (_QWORD *)*a2;
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids, a2);
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  *(_OWORD *)lpServiceConfig_8 = 0;
  v10 = 0;
  std::vector<unsigned char>::resize(lpServiceConfig_8, pcbBytesNeeded);
  v5 = lpServiceConfig_8[0];
  if ( !QueryServiceConfigW(hService, lpServiceConfig_8[0], pcbBytesNeeded, &pcbBytesNeeded) )
  {
    v6 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( a2[3] >= 8u )
        a2 = (_QWORD *)*a2;
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids,
        (_DWORD)a2,
        v6);
    }
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, v6);
    throw (HResultException *)pExceptionObject;
  }
  dwStartType = v5->dwStartType;
  std::vector<_NETSETUPPROPKEY>::_Tidy(lpServiceConfig_8);
  return dwStartType;
}

```

## disassembly

```asm
0x180052480  mov     rax, rsp
0x180052483  push    rbp
0x180052484  push    rsi
0x180052485  push    rdi
0x180052486  lea     rbp, [rax-48h]
0x18005248a  sub     rsp, 130h
0x180052491  mov     [rsp+140h+var_F8], 0FFFFFFFFFFFFFFFEh
0x18005249a  mov     [rax+18h], rbx
0x18005249e  mov     rax, cs:__security_cookie
0x1800524a5  xor     rax, rsp
0x1800524a8  mov     [rbp+40h+var_18], rax
0x1800524ac  mov     rbx, rdx
0x1800524af  mov     rsi, rcx
0x1800524b2  mov     [rbp+40h+pcbBytesNeeded], 0
0x1800524b9  lea     r9, [rbp+40h+pcbBytesNeeded]; pcbBytesNeeded
0x1800524bd  xor     r8d, r8d; cbBufSize
0x1800524c0  xor     edx, edx; lpServiceConfig
0x1800524c2  call    cs:__imp_QueryServiceConfigW
0x1800524c8  call    cs:__imp_GetLastError
0x1800524ce  cmp     eax, 7Ah ; 'z'
0x1800524d1  jz      short loc_18005253E
0x1800524d3  lea     rax, WPP_GLOBAL_Control
0x1800524da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800524e1  cmp     rcx, rax
0x1800524e4  jz      short loc_18005250E
0x1800524e6  cmp     byte ptr [rcx+19h], 2
0x1800524ea  jb      short loc_18005250E
0x1800524ec  cmp     qword ptr [rbx+18h], 8
0x1800524f1  jb      short loc_1800524F6
0x1800524f3  mov     rbx, [rbx]
0x1800524f6  mov     edx, 0Dh
0x1800524fb  mov     r9, rbx
0x1800524fe  lea     r8, WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids
0x180052505  mov     rcx, [rcx+10h]
0x180052509  call    WPP_SF_S
0x18005250e  call    cs:__imp_GetLastError
0x180052514  test    eax, eax
0x180052516  jle     short loc_180052520
0x180052518  movzx   eax, ax
0x18005251b  or      eax, 80070000h
0x180052520  mov     edx, eax; int
0x180052522  lea     rcx, [rsp+140h+pExceptionObject]; this
0x180052527  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18005252c  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180052533  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180052538  call    _CxxThrowException_0
0x18005253e  xorps   xmm0, xmm0
0x180052541  movdqu  xmmword ptr [rsp+140h+lpServiceConfig+8], xmm0
0x180052547  mov     [rsp+140h+var_100], 0
0x180052550  mov     edx, [rbp+40h+pcbBytesNeeded]
0x180052553  lea     rcx, [rsp+140h+lpServiceConfig+8]
0x180052558  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18005255d  mov     rdi, [rsp+140h+lpServiceConfig+8]
0x180052562  lea     r9, [rbp+40h+pcbBytesNeeded]; pcbBytesNeeded
0x180052566  mov     r8d, [rbp+40h+pcbBytesNeeded]; cbBufSize
0x18005256a  mov     rdx, rdi; lpServiceConfig
0x18005256d  mov     rcx, rsi; hService
0x180052570  call    cs:__imp_QueryServiceConfigW
0x180052576  test    eax, eax
0x180052578  jnz     short loc_1800525EC
0x18005257a  call    cs:__imp_GetLastError
0x180052580  mov     edi, eax
0x180052582  lea     rax, WPP_GLOBAL_Control
0x180052589  mov     rcx, cs:WPP_GLOBAL_Control
0x180052590  cmp     rcx, rax
0x180052593  jz      short loc_1800525C1
0x180052595  cmp     byte ptr [rcx+19h], 2
0x180052599  jb      short loc_1800525C1
0x18005259b  cmp     qword ptr [rbx+18h], 8
0x1800525a0  jb      short loc_1800525A5
0x1800525a2  mov     rbx, [rbx]
0x1800525a5  mov     edx, 0Eh
0x1800525aa  mov     [rsp+20h], edi
0x1800525ae  mov     r9, rbx
0x1800525b1  lea     r8, WPP_eecf0a69fc4a3f7219213d296c76a52c_Traceguids
0x1800525b8  mov     rcx, [rcx+10h]
0x1800525bc  call    WPP_SF_Sd
0x1800525c1  test    edi, edi
0x1800525c3  jle     short loc_1800525CE
0x1800525c5  movzx   edi, di
0x1800525c8  or      edi, 80070000h
0x1800525ce  mov     edx, edi; int
0x1800525d0  lea     rcx, [rsp+140h+pExceptionObject]; this
0x1800525d5  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800525da  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800525e1  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x1800525e6  call    _CxxThrowException_0
0x1800525ec  mov     ebx, [rdi+4]
0x1800525ef  lea     rcx, [rsp+140h+lpServiceConfig+8]
0x1800525f4  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x1800525f9  mov     eax, ebx
0x1800525fb  mov     rcx, [rbp+40h+var_18]
0x1800525ff  xor     rcx, rsp; StackCookie
0x180052602  call    __security_check_cookie
0x180052607  mov     rbx, [rsp+140h+arg_10]
0x18005260f  add     rsp, 130h
0x180052616  pop     rdi
0x180052617  pop     rsi
0x180052618  pop     rbp
0x180052619  retn
```
