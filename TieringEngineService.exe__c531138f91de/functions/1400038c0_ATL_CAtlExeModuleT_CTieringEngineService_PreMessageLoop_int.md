# ATL::CAtlExeModuleT<CTieringEngineService>::PreMessageLoop(int)

- ea: `0x1400038c0`
- end: `0x140003a88`
- name: `?PreMessageLoop@?$CAtlExeModuleT@VCTieringEngineService@@@ATL@@QEAAJH@Z`
- size: `456`
- prototype: `__int64 __fastcall(LPVOID lpParameter, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003e38`

## callees

- `0x1400038c0`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003a5c`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003a5c`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x1400039fb`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140003a2a`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x1400039fb`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140003a2a`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000394e`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000394e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400039ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003a22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400039ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003a22`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003a19`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003a19`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400039a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400039a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003a0b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140003a0b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400039dc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400039dc`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<CTieringEngineService>::PreMessageLoop(LPVOID lpParameter, DWORD a2)
{
  HRESULT v3; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rsi
  __int64 *v5; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v6; // r14
  bool v7; // zf
  HANDLE EventW; // rax
  HANDLE v9; // rsi
  HRESULT v10; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v11; // rdi
  __int64 *v12; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v13; // rdx
  LPUNKNOWN pUnk; // [rsp+50h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+58h] [rbp+10h] BYREF

  ThreadId = a2;
  v3 = 1;
  v4 = off_14004C200;
  v5 = off_14004C208;
  if ( off_14004C200 >= (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_14004C208 )
  {
    v7 = 0;
LABEL_15:
    if ( !v7 )
    {
      *((_BYTE *)lpParameter + 96) = 0;
      return (unsigned int)v3;
    }
    if ( *((_BYTE *)lpParameter + 96) )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)lpParameter + 10) = EventW;
      if ( !EventW )
      {
LABEL_20:
        v3 = -2147467259;
LABEL_26:
        v10 = 0;
        v11 = off_14004C200;
        v12 = off_14004C208;
        while ( v11 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v12 && !v10 )
        {
          v13 = *v11;
          if ( *v11 && *((_DWORD *)v13 + 10) )
          {
            v10 = CoRevokeClassObject(*((_DWORD *)v13 + 10));
            v12 = off_14004C208;
          }
          ++v11;
        }
        return (unsigned int)v3;
      }
      ThreadId = 0;
      v9 = CreateThread(0, 0, ATL::CAtlExeModuleT<CTieringEngineService>::MonitorProc, lpParameter, 0, &ThreadId);
      if ( !v9 )
      {
        CloseHandle(*((HANDLE *)lpParameter + 10));
        goto LABEL_20;
      }
      v3 = CoResumeClassObjects();
      if ( v3 < 0 )
      {
        SetEvent(*((HANDLE *)lpParameter + 10));
        WaitForSingleObject(v9, 2 * *((_DWORD *)lpParameter + 22));
      }
      CloseHandle(v9);
    }
    else
    {
      v3 = CoResumeClassObjects();
    }
    if ( v3 >= 0 )
      return (unsigned int)v3;
    goto LABEL_26;
  }
  while ( v3 >= 0 )
  {
    v6 = *v4;
    if ( *v4 )
    {
      pUnk = 0;
      if ( *((_QWORD *)v6 + 2) )
      {
        v3 = (*((__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))v6 + 2))(
               *((_QWORD *)v6 + 3),
               &GUID_00000000_0000_0000_c000_000000000046,
               &pUnk);
        if ( v3 >= 0 )
          v3 = CoRegisterClassObject(*(const IID *const *)v6, pUnk, 4u, 5u, (LPDWORD)v6 + 10);
        if ( pUnk )
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
        v5 = off_14004C208;
      }
      else
      {
        v3 = 0;
      }
    }
    if ( ++v4 >= (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
    {
      v7 = v3 == 0;
      if ( v3 >= 0 )
        goto LABEL_15;
      return (unsigned int)v3;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400038c0  mov     [rsp+arg_10], rbx
0x1400038c5  mov     [rsp+ThreadId], edx
0x1400038c9  push    rsi
0x1400038ca  push    rdi
0x1400038cb  push    r14
0x1400038cd  sub     rsp, 30h
0x1400038d1  mov     rdi, rcx
0x1400038d4  mov     ebx, 1
0x1400038d9  mov     rsi, cs:off_14004C200
0x1400038e0  mov     rax, cs:off_14004C208
0x1400038e7  cmp     rsi, rax
0x1400038ea  jnb     loc_140003989
0x1400038f0  test    ebx, ebx
0x1400038f2  js      loc_140003A78
0x1400038f8  mov     r14, [rsi]
0x1400038fb  test    r14, r14
0x1400038fe  jz      short loc_140003973
0x140003900  mov     [rsp+48h+pUnk], 0
0x140003909  cmp     qword ptr [r14+10h], 0
0x14000390e  jnz     short loc_140003914
0x140003910  xor     ebx, ebx
0x140003912  jmp     short loc_140003973
0x140003914  lea     r8, [rsp+48h+pUnk]
0x140003919  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140003920  mov     rcx, [r14+18h]
0x140003924  mov     rax, [r14+10h]
0x140003928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000392d  mov     ebx, eax
0x14000392f  test    eax, eax
0x140003931  js      short loc_140003956
0x140003933  lea     rax, [r14+28h]
0x140003937  mov     [rsp+48h+lpdwRegister], rax; lpdwRegister
0x14000393c  mov     r9d, 5; flags
0x140003942  lea     r8d, [r9-1]; dwClsContext
0x140003946  mov     rdx, [rsp+48h+pUnk]; pUnk
0x14000394b  mov     rcx, [r14]; rclsid
0x14000394e  call    cs:__imp_CoRegisterClassObject
0x140003954  mov     ebx, eax
0x140003956  mov     rcx, [rsp+48h+pUnk]
0x14000395b  test    rcx, rcx
0x14000395e  jz      short loc_14000396C
0x140003960  mov     rax, [rcx]
0x140003963  mov     rax, [rax+10h]
0x140003967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000396c  mov     rax, cs:off_14004C208
0x140003973  add     rsi, 8
0x140003977  cmp     rsi, rax
0x14000397a  jb      loc_1400038F0
0x140003980  test    ebx, ebx
0x140003982  jns     short loc_14000398B
0x140003984  jmp     loc_140003A78
0x140003989  test    ebx, ebx
0x14000398b  jnz     loc_140003A74
0x140003991  cmp     byte ptr [rdi+60h], 0
0x140003995  jz      loc_140003A2A
0x14000399b  xor     r9d, r9d; lpName
0x14000399e  xor     r8d, r8d; bInitialState
0x1400039a1  xor     edx, edx; bManualReset
0x1400039a3  xor     ecx, ecx; lpEventAttributes
0x1400039a5  call    cs:__imp_CreateEventW
0x1400039ab  mov     [rdi+50h], rax
0x1400039af  test    rax, rax
0x1400039b2  jz      short loc_1400039F4
0x1400039b4  mov     [rsp+48h+ThreadId], 0
0x1400039bc  lea     rax, [rsp+48h+ThreadId]
0x1400039c1  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x1400039c6  mov     dword ptr [rsp+48h+lpdwRegister], 0; dwCreationFlags
0x1400039ce  mov     r9, rdi; lpParameter
0x1400039d1  lea     r8, ?MonitorProc@?$CAtlExeModuleT@VCTieringEngineService@@@ATL@@SAKPEAX@Z; lpStartAddress
0x1400039d8  xor     edx, edx; dwStackSize
0x1400039da  xor     ecx, ecx; lpThreadAttributes
0x1400039dc  call    cs:__imp_CreateThread
0x1400039e2  mov     rsi, rax
0x1400039e5  test    rax, rax
0x1400039e8  jnz     short loc_1400039FB
0x1400039ea  mov     rcx, [rdi+50h]; hObject
0x1400039ee  call    cs:__imp_CloseHandle
0x1400039f4  mov     ebx, 80004005h
0x1400039f9  jmp     short loc_140003A36
0x1400039fb  call    cs:__imp_CoResumeClassObjects
0x140003a01  mov     ebx, eax
0x140003a03  test    eax, eax
0x140003a05  jns     short loc_140003A1F
0x140003a07  mov     rcx, [rdi+50h]; hEvent
0x140003a0b  call    cs:__imp_SetEvent
0x140003a11  mov     edx, [rdi+58h]
0x140003a14  add     edx, edx; dwMilliseconds
0x140003a16  mov     rcx, rsi; hHandle
0x140003a19  call    cs:__imp_WaitForSingleObject
0x140003a1f  mov     rcx, rsi; hObject
0x140003a22  call    cs:__imp_CloseHandle
0x140003a28  jmp     short loc_140003A32
0x140003a2a  call    cs:__imp_CoResumeClassObjects
0x140003a30  mov     ebx, eax
0x140003a32  test    ebx, ebx
0x140003a34  jns     short loc_140003A78
0x140003a36  xor     eax, eax
0x140003a38  mov     rdi, cs:off_14004C200
0x140003a3f  mov     rcx, cs:off_14004C208
0x140003a46  jmp     short loc_140003A6D
0x140003a48  test    eax, eax
0x140003a4a  jnz     short loc_140003A78
0x140003a4c  mov     rdx, [rdi]
0x140003a4f  test    rdx, rdx
0x140003a52  jz      short loc_140003A69
0x140003a54  cmp     [rdx+28h], eax
0x140003a57  jz      short loc_140003A69
0x140003a59  mov     ecx, [rdx+28h]; dwRegister
0x140003a5c  call    cs:__imp_CoRevokeClassObject
0x140003a62  mov     rcx, cs:off_14004C208
0x140003a69  add     rdi, 8
0x140003a6d  cmp     rdi, rcx
0x140003a70  jb      short loc_140003A48
0x140003a72  jmp     short loc_140003A78
0x140003a74  mov     byte ptr [rdi+60h], 0
0x140003a78  mov     eax, ebx
0x140003a7a  mov     rbx, [rsp+48h+arg_10]
0x140003a7f  add     rsp, 30h
0x140003a83  pop     r14
0x140003a85  pop     rdi
0x140003a86  pop     rsi
0x140003a87  retn
```
