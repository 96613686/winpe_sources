# CallerIdentity::GetCoreWindowForCallingThread(_GUID const &,void * *)

- ea: `0x180027720`
- end: `0x1800277fc`
- name: `?GetCoreWindowForCallingThread@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `220`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180027804`

## callees

- `0x18002748c`
- `0x180027678`
- `0x180027720`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallerTID` at `0x18002776d`
- `api-ms-win-core-com-l1-1-0!CoGetCallerTID` at `0x18002776d`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCoreWindowForCallingThread(
        CallerIdentity *this,
        const struct _GUID *a2,
        void **a3)
{
  CallerIdentity *v4; // rcx
  void **v5; // r8
  __int64 v6; // rdx
  HRESULT CoreApplicationForCallingProcess; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, _QWORD); // rbx
  __int64 v10; // rdx
  CallerIdentity *dwTID; // [rsp+40h] [rbp+20h] BYREF
  __int64 (__fastcall ***v13)(_QWORD, GUID *, const struct _GUID *); // [rsp+48h] [rbp+28h] BYREF
  struct _GUID v14; // [rsp+50h] [rbp+30h] BYREF

  dwTID = this;
  *(_QWORD *)&a2->Data1 = 0;
  *(_QWORD *)&v14.Data1 = 0;
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v14, a2);
  CoreApplicationForCallingProcess = CallerIdentity::GetCoreApplicationForCallingProcess(v4, &v14, v5);
  if ( CoreApplicationForCallingProcess >= 0 )
  {
    LODWORD(dwTID) = 0;
    CoreApplicationForCallingProcess = CoGetCallerTID((LPDWORD)&dwTID);
    if ( CoreApplicationForCallingProcess >= 0 )
    {
      if ( (((_DWORD)dwTID + 1) & 0xFFFFFFFE) != 0 )
      {
        v8 = *(_QWORD *)&v14.Data1;
        v13 = 0;
        v9 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(**(_QWORD **)&v14.Data1 + 64LL);
        Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v13, v6);
        CoreApplicationForCallingProcess = v9(v8, (unsigned int)dwTID, &v13);
        if ( CoreApplicationForCallingProcess >= 0 )
          CoreApplicationForCallingProcess = (**v13)(v13, &GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f, a2);
        Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v13, v10);
      }
      else
      {
        CoreApplicationForCallingProcess = -2147023728;
      }
    }
  }
  Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(&v14, v6);
  return (unsigned int)CoreApplicationForCallingProcess;
}

```

## disassembly

```asm
0x180027720  mov     qword ptr [rsp-18h+arg_10.Data4], rbx
0x180027725  mov     [rsp-18h+dwTID], rcx
0x18002772a  push    rbp
0x18002772b  push    rsi
0x18002772c  push    rdi
0x18002772d  mov     rbp, rsp
0x180027730  sub     rsp, 20h
0x180027734  lea     rcx, [rbp+arg_10]
0x180027738  mov     qword ptr [rdx], 0
0x18002773f  mov     rsi, rdx
0x180027742  mov     qword ptr [rbp+arg_10.Data1], 0
0x18002774a  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x18002774f  lea     rdx, [rbp+arg_10]; struct _GUID *
0x180027753  call    ?GetCoreApplicationForCallingProcess@CallerIdentity@@YAJAEBU_GUID@@PEAPEAX@Z; CallerIdentity::GetCoreApplicationForCallingProcess(_GUID const &,void * *)
0x180027758  mov     ebx, eax
0x18002775a  test    eax, eax
0x18002775c  js      loc_1800277E4
0x180027762  lea     rcx, [rbp+dwTID]; lpdwTID
0x180027766  mov     dword ptr [rbp+dwTID], 0
0x18002776d  call    cs:__imp_CoGetCallerTID
0x180027773  mov     ebx, eax
0x180027775  test    eax, eax
0x180027777  js      short loc_1800277E4
0x180027779  mov     eax, dword ptr [rbp+dwTID]
0x18002777c  inc     eax
0x18002777e  test    eax, 0FFFFFFFEh
0x180027783  jnz     short loc_18002778C
0x180027785  mov     ebx, 80070490h
0x18002778a  jmp     short loc_1800277E4
0x18002778c  mov     rdi, qword ptr [rbp+arg_10.Data1]
0x180027790  lea     rcx, [rbp+arg_8]
0x180027794  mov     [rbp+arg_8], 0
0x18002779c  mov     rax, [rdi]
0x18002779f  mov     rbx, [rax+40h]
0x1800277a3  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800277a8  mov     edx, dword ptr [rbp+dwTID]
0x1800277ab  lea     r8, [rbp+arg_8]
0x1800277af  mov     rcx, rdi
0x1800277b2  mov     rax, rbx
0x1800277b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277ba  mov     ebx, eax
0x1800277bc  test    eax, eax
0x1800277be  js      short loc_1800277DB
0x1800277c0  mov     rcx, [rbp+arg_8]
0x1800277c4  lea     rdx, _GUID_45d64a29_a63e_4cb6_b498_5781d298cb4f
0x1800277cb  mov     r8, rsi
0x1800277ce  mov     rax, [rcx]
0x1800277d1  mov     rax, [rax]
0x1800277d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277d9  mov     ebx, eax
0x1800277db  lea     rcx, [rbp+arg_8]
0x1800277df  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800277e4  lea     rcx, [rbp+arg_10]
0x1800277e8  call    ?InternalRelease@?$ComPtr@UICoreWindowInterop@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICoreWindowInterop>::InternalRelease(void)
0x1800277ed  mov     eax, ebx
0x1800277ef  mov     rbx, qword ptr [rsp+20h+arg_10.Data4]
0x1800277f4  add     rsp, 20h
0x1800277f8  pop     rdi
0x1800277f9  pop     rsi
0x1800277fa  pop     rbp
0x1800277fb  retn
```
