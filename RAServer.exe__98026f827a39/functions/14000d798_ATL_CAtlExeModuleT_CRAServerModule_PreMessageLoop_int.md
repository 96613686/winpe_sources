# ATL::CAtlExeModuleT<CRAServerModule>::PreMessageLoop(int)

- ea: `0x14000d798`
- end: `0x14000d8e2`
- name: `?PreMessageLoop@?$CAtlExeModuleT@VCRAServerModule@@@ATL@@QEAAJH@Z`
- size: `330`
- prototype: `__int64 __fastcall(IUnknown *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d990`

## callees

- `0x14000cbac`
- `0x14000cc50`
- `0x14000d798`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x14000d872`
- `KERNEL32!WaitForSingleObject` at `0x14000d872`
- `KERNEL32!CreateEventW` at `0x14000d7dd`
- `KERNEL32!CreateEventW` at `0x14000d7dd`
- `KERNEL32!CloseHandle` at `0x14000d837`
- `KERNEL32!CloseHandle` at `0x14000d837`
- `KERNEL32!SetEvent` at `0x14000d861`
- `KERNEL32!SetEvent` at `0x14000d861`
- `KERNEL32!CreateThread` at `0x14000d822`
- `KERNEL32!CreateThread` at `0x14000d822`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x14000d8b6`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x14000d8b6`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000d84e`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000d884`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000d84e`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000d884`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<CRAServerModule>::PreMessageLoop(IUnknown *a1, __int64 a2)
{
  __int64 result; // rax
  HRESULT v3; // ebx
  IUnknown *v4; // rax
  IUnknown *v5; // rdi
  struct ATL::_ATL_OBJMAP_ENTRY30 **v6; // rdi
  HRESULT v7; // eax
  __int64 *v8; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v9; // rdx
  IUnknown *v10; // [rsp+40h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF

  ThreadId = a2;
  v10 = a1;
  result = ATL::AtlComModuleRegisterClassObjects(a1, a2, 5u);
  v3 = result;
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result )
    {
      byte_140021DE0 = 0;
      return (unsigned int)v3;
    }
    if ( !byte_140021DE0 )
    {
      v3 = CoResumeClassObjects();
LABEL_13:
      if ( v3 < 0 )
      {
        v6 = off_1400211F0;
        v7 = 0;
        v8 = off_1400211F8;
        while ( v6 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v8 && !v7 )
        {
          v9 = *v6;
          if ( *v6 )
          {
            if ( *((_DWORD *)v9 + 10) )
            {
              v7 = CoRevokeClassObject(*((_DWORD *)v9 + 10));
              v8 = off_1400211F8;
            }
          }
          ++v6;
        }
      }
      return (unsigned int)v3;
    }
    hEvent = CreateEventW(0, 0, 0, 0);
    if ( hEvent )
    {
      ThreadId = 0;
      v4 = (IUnknown *)CreateThread(
                         0,
                         0,
                         (LPTHREAD_START_ROUTINE)ATL::CAtlExeModuleT<CRAServerModule>::MonitorProc,
                         &_AtlModule,
                         0,
                         &ThreadId);
      v5 = v4;
      if ( v4 )
      {
        v10 = v4;
        v3 = CoResumeClassObjects();
        if ( v3 < 0 )
        {
          SetEvent(hEvent);
          WaitForSingleObject(v5, 2 * dword_140021DD8);
        }
        goto LABEL_11;
      }
      CloseHandle(hEvent);
      v10 = 0;
    }
    else
    {
      v10 = 0;
    }
    v3 = -2147467259;
LABEL_11:
    ATL::CHandle::~CHandle((ATL::CHandle *)&v10);
    goto LABEL_13;
  }
  return result;
}

```

## disassembly

```asm
0x14000d798  mov     [rsp+arg_10], rbx
0x14000d79d  mov     [rsp+ThreadId], edx
0x14000d7a1  mov     [rsp+arg_0], rcx
0x14000d7a6  push    rdi
0x14000d7a7  sub     rsp, 30h
0x14000d7ab  mov     r8d, 5; unsigned int
0x14000d7b1  call    ?AtlComModuleRegisterClassObjects@ATL@@YAJPEAU_ATL_COM_MODULE70@1@KK@Z; ATL::AtlComModuleRegisterClassObjects(ATL::_ATL_COM_MODULE70 *,ulong,ulong)
0x14000d7b6  mov     ebx, eax
0x14000d7b8  test    eax, eax
0x14000d7ba  js      loc_14000D8D7
0x14000d7c0  jnz     loc_14000D8CE
0x14000d7c6  cmp     cs:byte_140021DE0, 0
0x14000d7cd  jz      loc_14000D884
0x14000d7d3  xor     r9d, r9d; lpName
0x14000d7d6  xor     r8d, r8d; bInitialState
0x14000d7d9  xor     edx, edx; bManualReset
0x14000d7db  xor     ecx, ecx; lpEventAttributes
0x14000d7dd  call    cs:__imp_CreateEventW
0x14000d7e3  mov     cs:hEvent, rax
0x14000d7ea  test    rax, rax
0x14000d7ed  jnz     short loc_14000D7F6
0x14000d7ef  mov     [rsp+38h+arg_0], rax
0x14000d7f4  jmp     short loc_14000D842
0x14000d7f6  lea     rax, [rsp+38h+ThreadId]
0x14000d7fb  mov     [rsp+38h+ThreadId], 0
0x14000d803  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14000d808  lea     r9, ?_AtlModule@@3VCRAServerModule@@A; lpParameter
0x14000d80f  lea     r8, ?MonitorProc@?$CAtlExeModuleT@VCRAServerModule@@@ATL@@SAKPEAX@Z; lpStartAddress
0x14000d816  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14000d81e  xor     edx, edx; dwStackSize
0x14000d820  xor     ecx, ecx; lpThreadAttributes
0x14000d822  call    cs:__imp_CreateThread
0x14000d828  mov     rdi, rax
0x14000d82b  test    rax, rax
0x14000d82e  jnz     short loc_14000D849
0x14000d830  mov     rcx, cs:hEvent; hObject
0x14000d837  call    cs:__imp_CloseHandle
0x14000d83d  mov     [rsp+38h+arg_0], rdi
0x14000d842  mov     ebx, 80004005h
0x14000d847  jmp     short loc_14000D878
0x14000d849  mov     [rsp+38h+arg_0], rdi
0x14000d84e  call    cs:__imp_CoResumeClassObjects
0x14000d854  mov     ebx, eax
0x14000d856  test    eax, eax
0x14000d858  jns     short loc_14000D878
0x14000d85a  mov     rcx, cs:hEvent; hEvent
0x14000d861  call    cs:__imp_SetEvent
0x14000d867  mov     edx, cs:dword_140021DD8
0x14000d86d  mov     rcx, rdi; hHandle
0x14000d870  add     edx, edx; dwMilliseconds
0x14000d872  call    cs:__imp_WaitForSingleObject
0x14000d878  lea     rcx, [rsp+38h+arg_0]; this
0x14000d87d  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x14000d882  jmp     short loc_14000D88C
0x14000d884  call    cs:__imp_CoResumeClassObjects
0x14000d88a  mov     ebx, eax
0x14000d88c  test    ebx, ebx
0x14000d88e  jns     short loc_14000D8D5
0x14000d890  mov     rdi, cs:off_1400211F0
0x14000d897  xor     eax, eax
0x14000d899  mov     rcx, cs:off_1400211F8
0x14000d8a0  jmp     short loc_14000D8C7
0x14000d8a2  test    eax, eax
0x14000d8a4  jnz     short loc_14000D8D5
0x14000d8a6  mov     rdx, [rdi]
0x14000d8a9  test    rdx, rdx
0x14000d8ac  jz      short loc_14000D8C3
0x14000d8ae  cmp     [rdx+28h], eax
0x14000d8b1  jz      short loc_14000D8C3
0x14000d8b3  mov     ecx, [rdx+28h]; dwRegister
0x14000d8b6  call    cs:__imp_CoRevokeClassObject
0x14000d8bc  mov     rcx, cs:off_1400211F8
0x14000d8c3  add     rdi, 8
0x14000d8c7  cmp     rdi, rcx
0x14000d8ca  jb      short loc_14000D8A2
0x14000d8cc  jmp     short loc_14000D8D5
0x14000d8ce  mov     cs:byte_140021DE0, 0
0x14000d8d5  mov     eax, ebx
0x14000d8d7  mov     rbx, [rsp+38h+arg_10]
0x14000d8dc  add     rsp, 30h
0x14000d8e0  pop     rdi
0x14000d8e1  retn
```
