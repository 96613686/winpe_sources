# ServiceBase::_ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x1800061a0`
- end: `0x1800062d5`
- name: `?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z`
- size: `309`
- prototype: `__int64 __fastcall(__int64 dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800035d0`

## callees

- `0x1800061a0`
- `0x180006548`
- `0x1800067bc`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800061dc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800062ab`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800062ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006268`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006268`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062cb`

## pseudocode

```c
__int64 __fastcall ServiceBase::_ServiceCtrlHandler(
        __int64 dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        char *lpContext)
{
  unsigned int v7; // ebx
  int v8; // eax
  int updated; // esi
  unsigned int v10; // ebx

  v7 = dwControl;
  if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x10) != 0 )
    McTemplateU0zq_EventWriteTransfer(
      dwControl,
      ServiceBaseServiceControlHandler,
      lpContext + 8,
      (unsigned int)dwControl);
  EnterCriticalSection((LPCRITICAL_SECTION)(lpContext + 136));
  if ( *((_DWORD *)lpContext + 32) )
    goto LABEL_16;
  switch ( v7 )
  {
    case 1u:
      goto LABEL_19;
    case 4u:
      goto LABEL_26;
    case 5u:
    case 0xFu:
LABEL_19:
      *((_DWORD *)lpContext + 32) = 1;
      if ( v7 == 15 || v7 == 5 )
        *((_DWORD *)lpContext + 33) = 1;
      updated = ServiceBase::_UpdateStatus((ServiceBase *)lpContext, 3u);
      SetEvent(*((HANDLE *)lpContext + 10));
      break;
    default:
      if ( v7 < 0x80 )
      {
        if ( !v7 )
          goto LABEL_26;
        v8 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, LPVOID))(*(_QWORD *)lpContext + 48LL))(
               lpContext,
               v7,
               dwEventType,
               lpEventData);
      }
      else
      {
        if ( v7 > 0xFF )
          goto LABEL_26;
        v8 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, LPVOID))(*(_QWORD *)lpContext + 40LL))(
               lpContext,
               v7,
               dwEventType,
               lpEventData);
      }
      updated = v8;
      if ( v8 == -2147467263 )
      {
        if ( v7 != 32 )
        {
          v10 = 120;
          goto LABEL_17;
        }
        if ( *((_DWORD *)lpContext + 32) )
        {
LABEL_16:
          v10 = 1115;
LABEL_17:
          LeaveCriticalSection((LPCRITICAL_SECTION)(lpContext + 136));
          return v10;
        }
        goto LABEL_26;
      }
      break;
  }
  if ( updated < 0 && v7 != 15 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(lpContext + 136));
    return (unsigned __int16)updated;
  }
LABEL_26:
  LeaveCriticalSection((LPCRITICAL_SECTION)(lpContext + 136));
  return 0;
}

```

## disassembly

```asm
0x1800061a0  push    rbx
0x1800061a2  push    rbp
0x1800061a3  push    rsi
0x1800061a4  push    rdi
0x1800061a5  push    r14
0x1800061a7  sub     rsp, 30h
0x1800061ab  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 10h
0x1800061b2  mov     rdi, r9
0x1800061b5  mov     rsi, r8
0x1800061b8  mov     r14d, edx
0x1800061bb  mov     ebx, ecx
0x1800061bd  jz      short loc_1800061D2
0x1800061bf  lea     r8, [r9+8]
0x1800061c3  mov     r9d, ecx
0x1800061c6  lea     rdx, ServiceBaseServiceControlHandler
0x1800061cd  call    McTemplateU0zq_EventWriteTransfer
0x1800061d2  lea     rbp, [rdi+88h]
0x1800061d9  mov     rcx, rbp; lpCriticalSection
0x1800061dc  call    cs:__imp_EnterCriticalSection
0x1800061e2  cmp     dword ptr [rdi+80h], 0
0x1800061e9  jnz     short loc_180006260
0x1800061eb  mov     eax, ebx
0x1800061ed  mov     edx, 3; unsigned int
0x1800061f2  sub     eax, 1
0x1800061f5  jz      loc_180006282
0x1800061fb  sub     eax, edx
0x1800061fd  jz      loc_1800062C8
0x180006203  sub     eax, 1
0x180006206  jz      short loc_180006282
0x180006208  cmp     eax, 0Ah
0x18000620b  jz      short loc_180006282
0x18000620d  cmp     ebx, 80h
0x180006213  jb      short loc_18000622A
0x180006215  cmp     ebx, 0FFh
0x18000621b  ja      loc_1800062C8
0x180006221  mov     rax, [rdi]
0x180006224  mov     rax, [rax+28h]
0x180006228  jmp     short loc_180006239
0x18000622a  test    ebx, ebx
0x18000622c  jz      loc_1800062C8
0x180006232  mov     rax, [rdi]
0x180006235  mov     rax, [rax+30h]
0x180006239  mov     r9, rsi
0x18000623c  mov     r8d, r14d
0x18000623f  mov     edx, ebx
0x180006241  mov     rcx, rdi
0x180006244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006249  mov     esi, eax
0x18000624b  cmp     eax, 80004001h
0x180006250  jnz     short loc_1800062B1
0x180006252  cmp     ebx, 20h ; ' '
0x180006255  jnz     short loc_18000627B
0x180006257  cmp     dword ptr [rdi+80h], 0
0x18000625e  jz      short loc_1800062C8
0x180006260  mov     ebx, 45Bh
0x180006265  mov     rcx, rbp; lpCriticalSection
0x180006268  call    cs:__imp_LeaveCriticalSection
0x18000626e  mov     eax, ebx
0x180006270  add     rsp, 30h
0x180006274  pop     r14
0x180006276  pop     rdi
0x180006277  pop     rsi
0x180006278  pop     rbp
0x180006279  pop     rbx
0x18000627a  retn
0x18000627b  mov     ebx, 78h ; 'x'
0x180006280  jmp     short loc_180006265
0x180006282  mov     eax, 1
0x180006287  mov     [rdi+80h], eax
0x18000628d  cmp     ebx, 0Fh
0x180006290  jz      short loc_180006297
0x180006292  cmp     ebx, 5
0x180006295  jnz     short loc_18000629D
0x180006297  mov     [rdi+84h], eax
0x18000629d  mov     rcx, rdi; this
0x1800062a0  call    ?_UpdateStatus@ServiceBase@@AEAAJK@Z; ServiceBase::_UpdateStatus(ulong)
0x1800062a5  mov     rcx, [rdi+50h]; hEvent
0x1800062a9  mov     esi, eax
0x1800062ab  call    cs:__imp_SetEvent
0x1800062b1  test    esi, esi
0x1800062b3  jns     short loc_1800062C8
0x1800062b5  cmp     ebx, 0Fh
0x1800062b8  jz      short loc_1800062C8
0x1800062ba  mov     rcx, rbp; lpCriticalSection
0x1800062bd  call    cs:__imp_LeaveCriticalSection
0x1800062c3  movzx   eax, si
0x1800062c6  jmp     short loc_180006270
0x1800062c8  mov     rcx, rbp; lpCriticalSection
0x1800062cb  call    cs:__imp_LeaveCriticalSection
0x1800062d1  xor     eax, eax
0x1800062d3  jmp     short loc_180006270
```
