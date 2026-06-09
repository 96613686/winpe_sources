# CRpcIOManagerServer::Init(INameService *,INameObject *,ulong,ulong)

- ea: `0x180019f80`
- end: `0x18001a106`
- name: `?Init@CRpcIOManagerServer@@UEAAJPEAUINameService@@PEAUINameObject@@KK@Z`
- size: `390`
- prototype: `__int64 __usercall@<rax>(CRpcIOManagerServer *__hidden this@<rcx>, struct INameService *@<rdx>, struct INameObject *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000f674`
- `0x180011c38`
- `0x180019f80`
- `0x180054968`
- `0x1800580d8`
- `0x180085010`

## import_xrefs

- `RPCRT4!UuidFromStringA` at `0x180019ff2`
- `RPCRT4!UuidFromStringA` at `0x180019ff2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001a0a8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001a0a8`

## string_xrefs

- `0x18001a01e`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18001a0e4`: `com\complus\dtc\dtc\cm\src\iomgrsrv.cpp`
- `0x18001a08e`: `Failed to check token for admin.`
- `0x18001a0c7`: `ConvertStringSidToSidW failed!`

## pseudocode

```c
__int64 __fastcall CRpcIOManagerServer::Init(
        CRpcIOManagerServer *this,
        struct INameService *a2,
        struct INameObject *a3,
        int a4,
        unsigned int a5)
{
  RPC_CSTR *v8; // r14
  unsigned int ServiceAccountSid; // ebx
  CRpcIOManagerServer *v10; // rcx
  RPC_STATUS v11; // ebp
  __int64 v12; // rdx
  const wchar_t *v13; // rax
  __int64 v14; // r9
  signed int LastError; // eax
  char *v17; // [rsp+28h] [rbp-40h]
  int v18; // [rsp+30h] [rbp-38h]

  *((_QWORD *)this + 8) = a2;
  *((_QWORD *)this + 9) = a3;
  v8 = (RPC_CSTR *)(*(__int64 (__fastcall **)(struct INameObject *))(*(_QWORD *)a3 + 32LL))(a3);
  *((_DWORD *)this + 14) = *(_DWORD *)(*((_QWORD *)this + 1) + 64LL);
  ServiceAccountSid = CRpcIOManagerServer::RegisterProtocolSequences(this, a4, a5);
  if ( !ServiceAccountSid )
  {
    (*(void (__fastcall **)(struct INameObject *, _QWORD))(*(_QWORD *)a3 + 48LL))(a3, *((unsigned int *)this + 20));
    v11 = UuidFromStringA(*v8, (UUID *)this + 1);
    if ( !v11 )
    {
      v12 = *((_QWORD *)this + 11);
      *((_DWORD *)this + 8) = 1;
      *((_QWORD *)this + 5) = (char *)this + 16;
      ServiceAccountSid = CRpcIOManagerServer::GetServiceAccountSid(
                            v10,
                            *(struct ITmInstance **)(v12 + 64),
                            (void **)this + 12);
      if ( (ServiceAccountSid & 0x80000000) == 0 )
      {
        if ( ConvertStringSidToSidW(L"S-1-5-86-615999462-62705297-2911207457-59056572-3668589837", (PSID *)this + 13) )
          return ServiceAccountSid;
        LastError = GetLastError();
        ServiceAccountSid = LastError;
        if ( LastError > 0 )
          ServiceAccountSid = (unsigned __int16)LastError | 0x80070000;
        v13 = L"ConvertStringSidToSidW failed!";
        v14 = 446;
      }
      else
      {
        v13 = L"Failed to check token for admin.";
        v14 = 439;
      }
      LODWORD(v17) = ServiceAccountSid;
      TraceStringInline(
        1,
        1,
        L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
        v14,
        L"CRpcIOManagerServer::Init",
        v17,
        v13);
      return ServiceAccountSid;
    }
    TraceStringInline(
      1,
      1,
      L"com\\complus\\dtc\\dtc\\cm\\src\\iomgrsrv.cpp",
      427,
      L"CRpcIOManagerServer::Init",
      0,
      L"Server::Init UuidFromStringFailed");
    DtcWriteToEventLoggerA(1u, 3u, 0x4000103Cu, 0, 0, "Server::Init UuidFromStringFailed", v18);
    return (unsigned int)RpcStatusToHresult(v11);
  }
  return ServiceAccountSid;
}

```

## disassembly

```asm
0x180019f80  push    rbx
0x180019f82  push    rbp
0x180019f83  push    rsi
0x180019f84  push    rdi
0x180019f85  push    r14
0x180019f87  sub     rsp, 40h
0x180019f8b  mov     [rcx+40h], rdx
0x180019f8f  mov     rdi, rcx
0x180019f92  mov     [rcx+48h], r8
0x180019f96  mov     ebx, r9d
0x180019f99  mov     rax, [r8]
0x180019f9c  mov     rcx, r8
0x180019f9f  mov     rsi, r8
0x180019fa2  mov     rax, [rax+20h]
0x180019fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fab  mov     rdx, [rdi+8]
0x180019faf  mov     rcx, rdi; this
0x180019fb2  mov     r8d, [rsp+68h+arg_20]; unsigned int
0x180019fba  mov     r14, rax
0x180019fbd  mov     r9d, [rdx+40h]
0x180019fc1  mov     edx, ebx; unsigned int
0x180019fc3  mov     [rdi+38h], r9d
0x180019fc7  call    ?RegisterProtocolSequences@CRpcIOManagerServer@@QEAAJKK@Z; CRpcIOManagerServer::RegisterProtocolSequences(ulong,ulong)
0x180019fcc  mov     ebx, eax
0x180019fce  test    eax, eax
0x180019fd0  jnz     loc_18001A0F9
0x180019fd6  mov     rcx, [rsi]
0x180019fd9  mov     edx, [rdi+50h]
0x180019fdc  mov     rax, [rcx+30h]
0x180019fe0  mov     rcx, rsi
0x180019fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fe8  mov     rcx, [r14]; StringUuid
0x180019feb  lea     rbx, [rdi+10h]
0x180019fef  mov     rdx, rbx; Uuid
0x180019ff2  call    cs:__imp_UuidFromStringA
0x180019ff8  mov     ebp, eax
0x180019ffa  mov     esi, 1
0x180019fff  test    eax, eax
0x18001a001  jz      short loc_18001A070
0x18001a003  lea     rcx, aCrpciomanagers_5; "CRpcIOManagerServer::Init"
0x18001a00a  mov     r9d, 1ABh
0x18001a010  lea     rax, aServerInitUuid_0; "Server::Init UuidFromStringFailed"
0x18001a017  mov     edx, esi
0x18001a019  mov     qword ptr [rsp+68h+var_38], rax; int
0x18001a01e  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18001a025  mov     [rsp+68h+var_40], 0
0x18001a02e  mov     [rsp+68h+var_48], rcx
0x18001a033  mov     ecx, esi
0x18001a035  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001a03a  lea     rax, aServerInitUuid; "Server::Init UuidFromStringFailed"
0x18001a041  xor     r9d, r9d; unsigned int
0x18001a044  mov     [rsp+68h+var_40], rax; char *
0x18001a049  lea     edx, [rsi+2]; unsigned int
0x18001a04c  mov     r8d, 4000103Ch; unsigned int
0x18001a052  mov     [rsp+68h+var_48], 0; void *
0x18001a05b  mov     ecx, esi; unsigned int
0x18001a05d  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x18001a062  mov     ecx, ebp; int
0x18001a064  call    ?RpcStatusToHresult@@YAJJ@Z; RpcStatusToHresult(long)
0x18001a069  mov     ebx, eax
0x18001a06b  jmp     loc_18001A0F9
0x18001a070  mov     rdx, [rdi+58h]
0x18001a074  lea     r8, [rdi+60h]; void **
0x18001a078  mov     [rdi+20h], esi
0x18001a07b  mov     [rdi+28h], rbx
0x18001a07f  mov     rdx, [rdx+40h]; struct ITmInstance *
0x18001a083  call    ?GetServiceAccountSid@CRpcIOManagerServer@@AEAAJPEAUITmInstance@@PEAPEAX@Z; CRpcIOManagerServer::GetServiceAccountSid(ITmInstance *,void * *)
0x18001a088  mov     ebx, eax
0x18001a08a  test    eax, eax
0x18001a08c  jns     short loc_18001A09D
0x18001a08e  lea     rax, aFailedToCheckT_1; "Failed to check token for admin."
0x18001a095  mov     r9d, 1B7h
0x18001a09b  jmp     short loc_18001A0D4
0x18001a09d  lea     rdx, [rdi+68h]; Sid
0x18001a0a1  lea     rcx, StringSid; "S-1-5-86-615999462-62705297-2911207457-"...
0x18001a0a8  call    cs:__imp_ConvertStringSidToSidW
0x18001a0ae  test    eax, eax
0x18001a0b0  jnz     short loc_18001A0F9
0x18001a0b2  call    cs:__imp_GetLastError
0x18001a0b8  mov     ebx, eax
0x18001a0ba  test    eax, eax
0x18001a0bc  jle     short loc_18001A0C7
0x18001a0be  movzx   ebx, ax
0x18001a0c1  or      ebx, 80070000h
0x18001a0c7  lea     rax, aConvertstrings; "ConvertStringSidToSidW failed!"
0x18001a0ce  mov     r9d, 1BEh
0x18001a0d4  mov     qword ptr [rsp+68h+var_38], rax
0x18001a0d9  lea     rcx, aCrpciomanagers_5; "CRpcIOManagerServer::Init"
0x18001a0e0  mov     dword ptr [rsp+68h+var_40], ebx
0x18001a0e4  lea     r8, aComComplusDtcD_34; "com\\complus\\dtc\\dtc\\cm\\src\\iomgrs"...
0x18001a0eb  mov     [rsp+68h+var_48], rcx
0x18001a0f0  mov     edx, esi
0x18001a0f2  mov     ecx, esi
0x18001a0f4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001a0f9  mov     eax, ebx
0x18001a0fb  add     rsp, 40h
0x18001a0ff  pop     r14
0x18001a101  pop     rdi
0x18001a102  pop     rsi
0x18001a103  pop     rbp
0x18001a104  pop     rbx
0x18001a105  retn
```
