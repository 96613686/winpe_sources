# EnsureFaxServiceIsStarted

- ea: `0x18002ebe4`
- end: `0x18002ed47`
- name: `EnsureFaxServiceIsStarted`
- size: `355`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180015040`
- `0x180026b04`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002db3c`
- `0x18002dc40`
- `0x18002de00`
- `0x18002ebe4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18002ed2d`
- `KERNEL32!SetLastError` at `0x18002ed2d`
- `KERNEL32!GetLastError` at `0x18002ece1`
- `KERNEL32!GetLastError` at `0x18002ece1`
- `ADVAPI32!StartServiceW` at `0x18002ecb9`
- `ADVAPI32!StartServiceW` at `0x18002ecb9`

## pseudocode

```c
__int64 __fastcall EnsureFaxServiceIsStarted(__int64 a1, const unsigned __int16 *a2)
{
  _QWORD *v2; // rcx
  DWORD v3; // ebx
  unsigned int v4; // edi
  DWORD LastError; // eax
  unsigned int v7; // [rsp+20h] [rbp-38h]
  __int64 v8; // [rsp+60h] [rbp+8h] BYREF
  SC_HANDLE hService; // [rsp+68h] [rbp+10h] BYREF
  SC_HANDLE hSCObject; // [rsp+70h] [rbp+18h] BYREF
  LPCWSTR ServiceArgVectors; // [rsp+78h] [rbp+20h] BYREF

  v8 = a1;
  ServiceArgVectors = L"/DelaySuicide";
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_db036311db36307996a98c23702218b2_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  hSCObject = 0;
  hService = 0;
  LODWORD(v8) = 0;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 2) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_(v2[2], 81, WPP_db036311db36307996a98c23702218b2_Traceguids);
  v3 = FaxOpenService((const unsigned __int16 *)v2, a2, &hSCObject, &hService, v7, 0x14u, (unsigned int *)&v8);
  if ( v3 )
    goto LABEL_18;
  v4 = 1;
  if ( (_DWORD)v8 != 4 )
  {
    if ( StartServiceW(hService, 1u, &ServiceArgVectors) )
    {
      v3 = WaitForServiceStopOrStart(hService);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
    }
  }
  FaxCloseService(hSCObject, hService);
  if ( v3 )
  {
LABEL_18:
    SetLastError(v3);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18002ebe4  mov     [rsp+arg_0], rcx
0x18002ebe9  push    rbx
0x18002ebea  push    rdi
0x18002ebeb  push    r15
0x18002ebed  sub     rsp, 40h
0x18002ebf1  lea     rax, aDelaysuicide; "/DelaySuicide"
0x18002ebf8  mov     [rsp+58h+ServiceArgVectors], rax
0x18002ebfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec04  lea     r15, WPP_GLOBAL_Control
0x18002ec0b  cmp     rcx, r15
0x18002ec0e  jz      short loc_18002EC38
0x18002ec10  test    byte ptr [rcx+1Ch], 2
0x18002ec14  jz      short loc_18002EC38
0x18002ec16  cmp     byte ptr [rcx+19h], 5
0x18002ec1a  jb      short loc_18002EC38
0x18002ec1c  mov     rcx, [rcx+10h]
0x18002ec20  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002ec27  mov     edx, 1Fh
0x18002ec2c  call    WPP_SF_
0x18002ec31  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec38  mov     [rsp+58h+hSCObject], 0
0x18002ec41  mov     [rsp+58h+hService], 0
0x18002ec4a  mov     dword ptr [rsp+58h+arg_0], 0
0x18002ec52  cmp     rcx, r15
0x18002ec55  jz      short loc_18002EC78
0x18002ec57  test    byte ptr [rcx+1Ch], 2
0x18002ec5b  jz      short loc_18002EC78
0x18002ec5d  cmp     byte ptr [rcx+19h], 5
0x18002ec61  jb      short loc_18002EC78
0x18002ec63  mov     rcx, [rcx+10h]
0x18002ec67  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002ec6e  mov     edx, 51h ; 'Q'
0x18002ec73  call    WPP_SF_
0x18002ec78  lea     rax, [rsp+58h+arg_0]
0x18002ec7d  mov     [rsp+58h+var_28], rax; unsigned int *
0x18002ec82  lea     r9, [rsp+58h+hService]; struct SC_HANDLE__ **
0x18002ec87  lea     r8, [rsp+58h+hSCObject]; struct SC_HANDLE__ **
0x18002ec8c  mov     [rsp+58h+dwDesiredAccess], 14h; dwDesiredAccess
0x18002ec94  call    ?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z; FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)
0x18002ec99  mov     ebx, eax
0x18002ec9b  test    eax, eax
0x18002ec9d  jnz     loc_18002ED2B
0x18002eca3  cmp     dword ptr [rsp+58h+arg_0], 4
0x18002eca8  lea     edi, [rax+1]
0x18002ecab  jz      short loc_18002ED18
0x18002ecad  mov     rcx, [rsp+58h+hService]; hService
0x18002ecb2  lea     r8, [rsp+58h+ServiceArgVectors]; lpServiceArgVectors
0x18002ecb7  mov     edx, edi; dwNumServiceArgs
0x18002ecb9  call    cs:__imp_StartServiceW
0x18002ecc0  nop     dword ptr [rax+rax+00h]
0x18002ecc5  test    eax, eax
0x18002ecc7  jnz     short loc_18002ED0C
0x18002ecc9  mov     rax, cs:WPP_GLOBAL_Control
0x18002ecd0  cmp     rax, r15
0x18002ecd3  jz      short loc_18002ED18
0x18002ecd5  test    byte ptr [rax+1Ch], 2
0x18002ecd9  jz      short loc_18002ED18
0x18002ecdb  cmp     byte ptr [rax+19h], 2
0x18002ecdf  jb      short loc_18002ED18
0x18002ece1  call    cs:__imp_GetLastError
0x18002ece8  nop     dword ptr [rax+rax+00h]
0x18002eced  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecf4  lea     edx, [rbx+52h]
0x18002ecf7  mov     r9d, eax
0x18002ecfa  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002ed01  mov     rcx, [rcx+10h]
0x18002ed05  call    WPP_SF_d
0x18002ed0a  jmp     short loc_18002ED18
0x18002ed0c  mov     rcx, [rsp+58h+hService]; hService
0x18002ed11  call    ?WaitForServiceStopOrStart@@YAKPEAUSC_HANDLE__@@HK@Z; WaitForServiceStopOrStart(SC_HANDLE__ *,int,ulong)
0x18002ed16  mov     ebx, eax
0x18002ed18  mov     rdx, [rsp+58h+hService]; SC_HANDLE
0x18002ed1d  mov     rcx, [rsp+58h+hSCObject]; hSCObject
0x18002ed22  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x18002ed27  test    ebx, ebx
0x18002ed29  jz      short loc_18002ED3B
0x18002ed2b  mov     ecx, ebx; dwErrCode
0x18002ed2d  call    cs:__imp_SetLastError
0x18002ed34  nop     dword ptr [rax+rax+00h]
0x18002ed39  xor     edi, edi
0x18002ed3b  mov     eax, edi
0x18002ed3d  add     rsp, 40h
0x18002ed41  pop     r15
0x18002ed43  pop     rdi
0x18002ed44  pop     rbx
0x18002ed45  retn
```
