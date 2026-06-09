# ClientsTracker::Register(ulong,MapsClientType,void *)

- ea: `0x180009e8c`
- end: `0x18000a190`
- name: `?Register@ClientsTracker@@QEAAJKW4MapsClientType@@PEAX@Z`
- size: `772`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012cf0`

## callees

- `0x180003410`
- `0x180009128`
- `0x180009e8c`
- `0x18000b1c8`
- `0x18000b220`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009f51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009f51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a0e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a14d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a0e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a14d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009ed8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009ed8`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000a11b`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18000a11b`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000a0d5`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000a0d5`
- `ZTrace_Maps!ZTraceHelper` at `0x180009fa9`
- `ZTrace_Maps!ZTraceHelper` at `0x180009fa9`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180009f1a`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180009f1a`

## string_xrefs

- `0x180009f88`: `Attaching new client - type: %d | processId: %lu | moshost: %lu | odml: %lu | deleteAll: %lu | background: %lu | mapsStorage: %lu`

## pseudocode

```c
__int64 __fastcall ClientsTracker::Register(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  __int64 v8; // rcx
  __int64 v9; // r8
  char v10; // di
  int v11; // esi
  int v12; // eax
  int v13; // r8d
  int v14; // eax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rcx
  _QWORD v22[2]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v23[16]; // [rsp+70h] [rbp-58h] BYREF

  if ( (a3 & 0xFFFFFFFA) != 0 )
  {
    if ( a4 )
      __int2c();
    if ( a2 )
LABEL_10:
      __int2c();
  }
  else
  {
    if ( !a4 )
      __int2c();
    if ( a2 == GetCurrentProcessId() || !a2 )
      goto LABEL_10;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)qword_180035648 + 16LL))(qword_180035648) )
  {
    v10 = 0;
    v11 = ZTraceReportOrigination(-2147023641, "ClientsTracker::Register", 175, (const void *)a1);
LABEL_46:
    if ( v11 < 0
      && v10
      && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)qword_180035648 + 24LL))(qword_180035648) )
    {
      ZTraceReportIgnore(-2143748095, "ClientsTracker::Register", 234, (const void *)a1);
    }
    return (unsigned int)v11;
  }
  v10 = 1;
  if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v8, RegisterClient, v9, 1, v22);
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  v22[0] = a1;
  ZTraceHelper(
    1,
    "ClientsTracker::Register",
    185,
    a1,
    "Attaching new client - type: %d | processId: %lu | moshost: %lu | odml: %lu | deleteAll: %lu | background: %lu | mapsStorage: %lu",
    a3,
    a2,
    *(_DWORD *)(a1 + 116),
    *(_DWORD *)(a1 + 108),
    *(_DWORD *)(a1 + 120),
    *(_DWORD *)(a1 + 104),
    *(_DWORD *)(a1 + 124));
  switch ( a3 )
  {
    case 0u:
      v12 = ClientsTracker::AddToClientsMap(a1, a2, 0, a4);
      if ( v12 >= 0 )
      {
        if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(v18, IncrementClientCount, v19, 1, v23);
        ++*(_DWORD *)(a1 + 116);
        break;
      }
      v13 = 212;
      goto LABEL_45;
    case 1u:
      if ( *(_DWORD *)(a1 + 108) )
        __int2c();
      v12 = ClientsTracker::AddToClientsMap(a1, a2, 1, a4);
      if ( v12 >= 0 )
      {
        if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(v16, IncrementOdmlClientCount, v17, 1, v22);
        ++*(_DWORD *)(a1 + 108);
        break;
      }
      v13 = 196;
LABEL_45:
      v11 = ZTraceReportPropagation(v12, "ClientsTracker::Register", v13, (const void *)a1);
      LeaveCriticalSection((LPCRITICAL_SECTION)a1);
      goto LABEL_46;
    case 2u:
      v15 = *(_DWORD *)(a1 + 104);
      if ( v15 )
        __int2c();
      *(_DWORD *)(a1 + 104) = v15 + 1;
      break;
    case 3u:
      v14 = *(_DWORD *)(a1 + 120);
      if ( v14 )
        __int2c();
      *(_DWORD *)(a1 + 120) = v14 + 1;
      break;
    case 4u:
      if ( *(_DWORD *)(a1 + 124) )
        __int2c();
      v12 = ClientsTracker::AddToClientsMap(a1, a2, 4, a4);
      if ( v12 < 0 )
      {
        v13 = 219;
        goto LABEL_45;
      }
      ++*(_DWORD *)(a1 + 124);
      break;
    case 5u:
      v12 = ClientsTracker::AddToClientsMap(a1, a2, 5, a4);
      if ( v12 < 0 )
      {
        v13 = 202;
        goto LABEL_45;
      }
      ++*(_DWORD *)(a1 + 112);
      break;
    default:
      __int2c();
      break;
  }
  v11 = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  if ( (Microsoft_Windows_MosHostEnableBits & 1) != 0 )
    McTemplateU0qq_EventWriteTransfer(v20, RegisterClient_Info, a2, a3);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180009e8c  push    rbx
0x180009e8e  push    rbp
0x180009e8f  push    rsi
0x180009e90  push    rdi
0x180009e91  push    r14
0x180009e93  push    r15
0x180009e95  sub     rsp, 98h
0x180009e9c  mov     rax, cs:__security_cookie
0x180009ea3  xor     rax, rsp
0x180009ea6  mov     [rsp+0C8h+var_48], rax
0x180009eae  mov     rsi, r9
0x180009eb1  mov     r15d, r8d
0x180009eb4  mov     ebp, edx
0x180009eb6  mov     rbx, rcx
0x180009eb9  test    r8d, 0FFFFFFFAh
0x180009ec0  jz      short loc_180009ED1
0x180009ec2  test    r9, r9
0x180009ec5  jz      short loc_180009EC9
0x180009ec7  int     2Ch; Windows NT - assertion failure
0x180009ec9  test    ebp, ebp
0x180009ecb  jz      short loc_180009EE8
0x180009ecd  int     2Ch; Windows NT - assertion failure
0x180009ecf  jmp     short loc_180009EE8
0x180009ed1  test    rsi, rsi
0x180009ed4  jnz     short loc_180009ED8
0x180009ed6  int     2Ch; Windows NT - assertion failure
0x180009ed8  call    cs:__imp_GetCurrentProcessId
0x180009ede  cmp     ebp, eax
0x180009ee0  jz      short loc_180009EE6
0x180009ee2  test    ebp, ebp
0x180009ee4  jnz     short loc_180009EE8
0x180009ee6  int     2Ch; Windows NT - assertion failure
0x180009ee8  mov     rcx, cs:qword_180035648
0x180009eef  mov     rax, [rcx]
0x180009ef2  mov     rax, [rax+10h]
0x180009ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009efb  test    eax, eax
0x180009efd  jnz     short loc_180009F27
0x180009eff  xor     dil, dil
0x180009f02  mov     r9, rbx
0x180009f05  mov     r8d, 0AFh
0x180009f0b  lea     r14, aClientstracker_1; "ClientsTracker::Register"
0x180009f12  mov     rdx, r14
0x180009f15  mov     ecx, 800704E7h
0x180009f1a  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180009f20  mov     esi, eax
0x180009f22  jmp     loc_18000A0E6
0x180009f27  mov     edi, 1
0x180009f2c  test    cs:Microsoft_Windows_MosHostEnableBits, dil
0x180009f33  jz      short loc_180009F4E
0x180009f35  lea     rax, [rsp+0C8h+var_68]
0x180009f3a  mov     [rsp+0C8h+var_A8], rax
0x180009f3f  mov     r9d, edi
0x180009f42  lea     rdx, RegisterClient
0x180009f49  call    McGenEventWrite_EventWriteTransfer
0x180009f4e  mov     rcx, rbx; lpCriticalSection
0x180009f51  call    cs:__imp_EnterCriticalSection
0x180009f57  mov     [rsp+0C8h+var_68], rbx
0x180009f5c  mov     eax, [rbx+7Ch]
0x180009f5f  mov     [rsp+0C8h+var_70], eax
0x180009f63  mov     eax, [rbx+68h]
0x180009f66  mov     [rsp+0C8h+var_78], eax
0x180009f6a  mov     eax, [rbx+78h]
0x180009f6d  mov     [rsp+0C8h+var_80], eax
0x180009f71  mov     eax, [rbx+6Ch]
0x180009f74  mov     [rsp+0C8h+var_88], eax
0x180009f78  mov     eax, [rbx+74h]
0x180009f7b  mov     [rsp+0C8h+var_90], eax
0x180009f7f  mov     [rsp+0C8h+var_98], ebp
0x180009f83  mov     [rsp+0C8h+var_A0], r15d
0x180009f88  lea     rax, aAttachingNewCl; "Attaching new client - type: %d | proce"...
0x180009f8f  mov     [rsp+0C8h+var_A8], rax
0x180009f94  mov     r9, rbx
0x180009f97  mov     r8d, 0B9h
0x180009f9d  lea     r14, aClientstracker_1; "ClientsTracker::Register"
0x180009fa4  mov     rdx, r14
0x180009fa7  mov     ecx, edi
0x180009fa9  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x180009faf  mov     ecx, r15d
0x180009fb2  test    r15d, r15d
0x180009fb5  jz      loc_18000A0B3
0x180009fbb  sub     ecx, 1
0x180009fbe  jz      loc_18000A065
0x180009fc4  sub     ecx, 1
0x180009fc7  jz      loc_18000A052
0x180009fcd  sub     ecx, 1
0x180009fd0  jz      short loc_18000A03F
0x180009fd2  sub     ecx, 1
0x180009fd5  jz      short loc_18000A00D
0x180009fd7  cmp     ecx, 1
0x180009fda  jz      short loc_180009FE3
0x180009fdc  int     2Ch; Windows NT - assertion failure
0x180009fde  jmp     loc_18000A148
0x180009fe3  mov     r9, rsi
0x180009fe6  mov     r8d, 5
0x180009fec  mov     edx, ebp
0x180009fee  mov     rcx, rbx
0x180009ff1  call    ?AddToClientsMap@ClientsTracker@@AEAAJKW4MapsClientType@@PEAX@Z; ClientsTracker::AddToClientsMap(ulong,MapsClientType,void *)
0x180009ff6  test    eax, eax
0x180009ff8  jns     short loc_18000A005
0x180009ffa  mov     r8d, 0CAh
0x18000a000  jmp     loc_18000A0CD
0x18000a005  add     [rbx+70h], edi
0x18000a008  jmp     loc_18000A148
0x18000a00d  cmp     dword ptr [rbx+7Ch], 0
0x18000a011  jz      short loc_18000A015
0x18000a013  int     2Ch; Windows NT - assertion failure
0x18000a015  mov     r9, rsi
0x18000a018  mov     r8d, 4
0x18000a01e  mov     edx, ebp
0x18000a020  mov     rcx, rbx
0x18000a023  call    ?AddToClientsMap@ClientsTracker@@AEAAJKW4MapsClientType@@PEAX@Z; ClientsTracker::AddToClientsMap(ulong,MapsClientType,void *)
0x18000a028  test    eax, eax
0x18000a02a  jns     short loc_18000A037
0x18000a02c  mov     r8d, 0DBh
0x18000a032  jmp     loc_18000A0CD
0x18000a037  add     [rbx+7Ch], edi
0x18000a03a  jmp     loc_18000A148
0x18000a03f  mov     eax, [rbx+78h]
0x18000a042  test    eax, eax
0x18000a044  jz      short loc_18000A048
0x18000a046  int     2Ch; Windows NT - assertion failure
0x18000a048  inc     eax
0x18000a04a  mov     [rbx+78h], eax
0x18000a04d  jmp     loc_18000A148
0x18000a052  mov     eax, [rbx+68h]
0x18000a055  test    eax, eax
0x18000a057  jz      short loc_18000A05B
0x18000a059  int     2Ch; Windows NT - assertion failure
0x18000a05b  inc     eax
0x18000a05d  mov     [rbx+68h], eax
0x18000a060  jmp     loc_18000A148
0x18000a065  cmp     dword ptr [rbx+6Ch], 0
0x18000a069  jz      short loc_18000A06D
0x18000a06b  int     2Ch; Windows NT - assertion failure
0x18000a06d  mov     r9, rsi
0x18000a070  mov     r8d, edi
0x18000a073  mov     edx, ebp
0x18000a075  mov     rcx, rbx
0x18000a078  call    ?AddToClientsMap@ClientsTracker@@AEAAJKW4MapsClientType@@PEAX@Z; ClientsTracker::AddToClientsMap(ulong,MapsClientType,void *)
0x18000a07d  test    eax, eax
0x18000a07f  jns     short loc_18000A089
0x18000a081  mov     r8d, 0C4h
0x18000a087  jmp     short loc_18000A0CD
0x18000a089  test    cs:Microsoft_Windows_MosHostEnableBits, dil
0x18000a090  jz      short loc_18000A0AB
0x18000a092  lea     rax, [rsp+0C8h+var_68]
0x18000a097  mov     [rsp+0C8h+var_A8], rax
0x18000a09c  mov     r9d, edi
0x18000a09f  lea     rdx, IncrementOdmlClientCount
0x18000a0a6  call    McGenEventWrite_EventWriteTransfer
0x18000a0ab  add     [rbx+6Ch], edi
0x18000a0ae  jmp     loc_18000A148
0x18000a0b3  mov     r9, rsi
0x18000a0b6  xor     r8d, r8d
0x18000a0b9  mov     edx, ebp
0x18000a0bb  mov     rcx, rbx
0x18000a0be  call    ?AddToClientsMap@ClientsTracker@@AEAAJKW4MapsClientType@@PEAX@Z; ClientsTracker::AddToClientsMap(ulong,MapsClientType,void *)
0x18000a0c3  test    eax, eax
0x18000a0c5  jns     short loc_18000A123
0x18000a0c7  mov     r8d, 0D4h
0x18000a0cd  mov     r9, rbx
0x18000a0d0  mov     rdx, r14
0x18000a0d3  mov     ecx, eax
0x18000a0d5  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000a0db  mov     esi, eax
0x18000a0dd  mov     rcx, rbx; lpCriticalSection
0x18000a0e0  call    cs:__imp_LeaveCriticalSection
0x18000a0e6  test    esi, esi
0x18000a0e8  jns     loc_18000A16E
0x18000a0ee  test    dil, dil
0x18000a0f1  jz      short loc_18000A16E
0x18000a0f3  mov     rcx, cs:qword_180035648
0x18000a0fa  mov     rax, [rcx]
0x18000a0fd  mov     rax, [rax+18h]
0x18000a101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a106  test    eax, eax
0x18000a108  jnz     short loc_18000A16E
0x18000a10a  mov     r9, rbx
0x18000a10d  mov     r8d, 0EAh
0x18000a113  mov     rdx, r14
0x18000a116  mov     ecx, 80390001h
0x18000a11b  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18000a121  jmp     short loc_18000A16E
0x18000a123  test    cs:Microsoft_Windows_MosHostEnableBits, dil
0x18000a12a  jz      short loc_18000A145
0x18000a12c  lea     rax, [rsp+0C8h+var_58]
0x18000a131  mov     [rsp+0C8h+var_A8], rax
0x18000a136  mov     r9d, edi
0x18000a139  lea     rdx, IncrementClientCount
0x18000a140  call    McGenEventWrite_EventWriteTransfer
0x18000a145  add     [rbx+74h], edi
0x18000a148  xor     esi, esi
0x18000a14a  mov     rcx, rbx; lpCriticalSection
0x18000a14d  call    cs:__imp_LeaveCriticalSection
0x18000a153  test    cs:Microsoft_Windows_MosHostEnableBits, dil
0x18000a15a  jz      short loc_18000A16E
0x18000a15c  mov     r9d, r15d
0x18000a15f  mov     r8d, ebp
0x18000a162  lea     rdx, RegisterClient_Info
0x18000a169  call    McTemplateU0qq_EventWriteTransfer
0x18000a16e  mov     eax, esi
0x18000a170  mov     rcx, [rsp+0C8h+var_48]
0x18000a178  xor     rcx, rsp; StackCookie
0x18000a17b  call    __security_check_cookie
0x18000a180  add     rsp, 98h
0x18000a187  pop     r15
0x18000a189  pop     r14
0x18000a18b  pop     rdi
0x18000a18c  pop     rsi
0x18000a18d  pop     rbp
0x18000a18e  pop     rbx
0x18000a18f  retn
```
