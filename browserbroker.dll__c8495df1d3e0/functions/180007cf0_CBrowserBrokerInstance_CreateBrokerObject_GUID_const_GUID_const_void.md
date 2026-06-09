# CBrowserBrokerInstance::CreateBrokerObject(_GUID const &,_GUID const &,void * *)

- ea: `0x180007cf0`
- end: `0x180007e97`
- name: `?CreateBrokerObject@CBrowserBrokerInstance@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `423`
- prototype: `__int64 __fastcall(CBrowserBrokerInstance *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800082e0`

## callees

- `0x180007cf0`
- `0x180008938`
- `0x18000a2dc`
- `0x18000b6d0`
- `0x18000e428`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007d63`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007d63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007d8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007d8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007e09`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007e09`

## string_xrefs

- `0x180007d56`: `wininet.dll`
- `0x180007d82`: `DllGetClassObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CBrowserBrokerInstance::CreateBrokerObject(
        CBrowserBrokerInstance *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  int PIC; // ebx
  HMODULE Library; // rax
  HMODULE v11; // rsi
  signed __int32 v12; // ebp
  FARPROC ProcAddress; // rax
  unsigned int v15; // edx
  __int128 *v16; // rcx
  __int64 v17; // rsi
  __int64 v18; // rax
  __int64 v20; // [rsp+78h] [rbp+20h] BYREF

  *a4 = 0;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&CLSID_WininetBroker.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&CLSID_WininetBroker.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)CLSID_WininetBroker.Data4;
  if ( v6 )
  {
    v15 = 0;
    PIC = -2147024891;
    while ( v15 < 5 )
    {
      v16 = &xmmword_18003FE70[v15];
      v17 = v15;
      v18 = *(_QWORD *)&a2->Data1 - *(_QWORD *)v16;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)v16 )
        v18 = *(_QWORD *)a2->Data4 - *((_QWORD *)v16 + 1);
      if ( !v18 )
      {
        PIC = CBrowserBrokerInstance::EnsureAggregateAuthorizeCaller((struct IUnknown *)this, v15);
        if ( PIC < 0 )
          return (unsigned int)PIC;
        if ( *((_QWORD *)this + v17 + 144) )
          return (unsigned int)CBrowserBrokerInstance::QueryInterface((struct IUnknown *)this, a3, a4);
        return (unsigned int)-2147024891;
      }
      ++v15;
    }
  }
  else
  {
    LODWORD(v20) = 0;
    PIC = BrokerAuthenticateAttachedCallerGetPIC(2, (unsigned int *)&v20);
    if ( PIC >= 0 )
    {
      Library = LoadLibraryExW(L"wininet.dll", 0, 0x800u);
      v11 = Library;
      if ( Library )
      {
        v12 = _InterlockedIncrement((volatile signed __int32 *)this + 280);
        ProcAddress = GetProcAddress(Library, "DllGetClassObject");
        if ( ProcAddress )
        {
          v20 = 0;
          PIC = ((__int64 (__fastcall *)(const struct _GUID *, GUID *, __int64 *))ProcAddress)(
                  a2,
                  &GUID_00000001_0000_0000_c000_000000000046,
                  &v20);
          if ( PIC >= 0 )
          {
            PIC = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v20 + 24LL))(
                    v20,
                    0,
                    a3,
                    a4);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
        }
        else
        {
          PIC = HRESULTFromLastErrorError();
        }
        if ( v12 == 1 )
        {
          *((_QWORD *)this + 141) = v11;
        }
        else
        {
          _InterlockedDecrement((volatile signed __int32 *)this + 280);
          FreeLibrary(v11);
        }
      }
      else
      {
        return (unsigned int)HRESULTFromLastErrorError();
      }
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180007cf0  mov     [rsp+arg_0], rbx
0x180007cf5  mov     [rsp+arg_8], rbp
0x180007cfa  push    rsi
0x180007cfb  push    rdi
0x180007cfc  push    r12
0x180007cfe  push    r14
0x180007d00  push    r15
0x180007d02  sub     rsp, 30h
0x180007d06  mov     qword ptr [r9], 0
0x180007d0d  mov     r15, r9
0x180007d10  mov     rax, [rdx]
0x180007d13  mov     r12, r8
0x180007d16  sub     rax, qword ptr cs:CLSID_WininetBroker.Data1
0x180007d1d  mov     r14, rdx
0x180007d20  mov     rdi, rcx
0x180007d23  jnz     short loc_180007D30
0x180007d25  mov     rax, [rdx+8]
0x180007d29  sub     rax, qword ptr cs:CLSID_WininetBroker.Data4
0x180007d30  test    rax, rax
0x180007d33  jnz     loc_180007E18
0x180007d39  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x180007d3e  mov     dword ptr [rsp+58h+arg_18], eax
0x180007d42  lea     ecx, [rax+2]; unsigned int
0x180007d45  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x180007d4a  mov     ebx, eax
0x180007d4c  test    eax, eax
0x180007d4e  js      loc_180007E7E
0x180007d54  xor     edx, edx; hFile
0x180007d56  lea     rcx, LibFileName; "wininet.dll"
0x180007d5d  mov     r8d, 800h; dwFlags
0x180007d63  call    cs:__imp_LoadLibraryExW
0x180007d69  mov     rsi, rax
0x180007d6c  test    rax, rax
0x180007d6f  jz      loc_180007E11
0x180007d75  mov     ebp, 1
0x180007d7a  lock xadd [rdi+460h], ebp
0x180007d82  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x180007d89  mov     rcx, rax; hModule
0x180007d8c  inc     ebp
0x180007d8e  call    cs:__imp_GetProcAddress
0x180007d94  test    rax, rax
0x180007d97  jz      short loc_180007DEA
0x180007d99  lea     r8, [rsp+58h+arg_18]
0x180007d9e  mov     [rsp+58h+arg_18], 0
0x180007da7  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x180007dae  mov     rcx, r14
0x180007db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007db6  mov     ebx, eax
0x180007db8  test    eax, eax
0x180007dba  js      short loc_180007DF1
0x180007dbc  mov     rcx, [rsp+58h+arg_18]
0x180007dc1  mov     r9, r15
0x180007dc4  mov     r8, r12
0x180007dc7  xor     edx, edx
0x180007dc9  mov     rax, [rcx]
0x180007dcc  mov     rax, [rax+18h]
0x180007dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dd5  mov     rcx, [rsp+58h+arg_18]
0x180007dda  mov     ebx, eax
0x180007ddc  mov     rax, [rcx]
0x180007ddf  mov     rax, [rax+10h]
0x180007de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007de8  jmp     short loc_180007DF1
0x180007dea  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180007def  mov     ebx, eax
0x180007df1  cmp     ebp, 1
0x180007df4  jnz     short loc_180007DFF
0x180007df6  mov     [rdi+468h], rsi
0x180007dfd  jmp     short loc_180007E7E
0x180007dff  lock dec dword ptr [rdi+460h]
0x180007e06  mov     rcx, rsi; hLibModule
0x180007e09  call    cs:__imp_FreeLibrary
0x180007e0f  jmp     short loc_180007E7E
0x180007e11  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180007e16  jmp     short loc_180007E78
0x180007e18  mov     ebp, 80070005h
0x180007e1d  xor     edx, edx; unsigned int
0x180007e1f  mov     ebx, ebp
0x180007e21  cmp     edx, 5
0x180007e24  jnb     short loc_180007E7E
0x180007e26  lea     rax, xmmword_18003FE70
0x180007e2d  mov     ecx, edx
0x180007e2f  shl     rcx, 4
0x180007e33  add     rcx, rax
0x180007e36  mov     esi, edx
0x180007e38  mov     rax, [r14]
0x180007e3b  sub     rax, [rcx]
0x180007e3e  jnz     short loc_180007E48
0x180007e40  mov     rax, [r14+8]
0x180007e44  sub     rax, [rcx+8]
0x180007e48  test    rax, rax
0x180007e4b  jz      short loc_180007E51
0x180007e4d  inc     edx
0x180007e4f  jmp     short loc_180007E21
0x180007e51  mov     rcx, rdi; this
0x180007e54  call    ?EnsureAggregateAuthorizeCaller@CBrowserBrokerInstance@@QEAAJK@Z; CBrowserBrokerInstance::EnsureAggregateAuthorizeCaller(ulong)
0x180007e59  mov     ebx, eax
0x180007e5b  test    eax, eax
0x180007e5d  js      short loc_180007E7E
0x180007e5f  cmp     qword ptr [rdi+rsi*8+480h], 0
0x180007e68  jz      short loc_180007E7C
0x180007e6a  mov     r8, r15; void **
0x180007e6d  mov     rdx, r12; struct _GUID *
0x180007e70  mov     rcx, rdi; this
0x180007e73  call    ?QueryInterface@CBrowserBrokerInstance@@UEAAJAEBU_GUID@@PEAPEAX@Z; CBrowserBrokerInstance::QueryInterface(_GUID const &,void * *)
0x180007e78  mov     ebx, eax
0x180007e7a  jmp     short loc_180007E7E
0x180007e7c  mov     ebx, ebp
0x180007e7e  mov     rbp, [rsp+58h+arg_8]
0x180007e83  mov     eax, ebx
0x180007e85  mov     rbx, [rsp+58h+arg_0]
0x180007e8a  add     rsp, 30h
0x180007e8e  pop     r15
0x180007e90  pop     r14
0x180007e92  pop     r12
0x180007e94  pop     rdi
0x180007e95  pop     rsi
0x180007e96  retn
```
