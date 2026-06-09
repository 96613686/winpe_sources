# ServiceControlHandler(ulong,ulong,void *,void *)

- ea: `0x1800211d0`
- end: `0x1800212a3`
- name: `?ServiceControlHandler@@YAKKKPEAX0@Z`
- size: `211`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180010b64`
- `0x180011afc`
- `0x1800211d0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021282`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180021282`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002124a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002124a`

## string_xrefs

- `0x180021291`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180021259`: `onecoreuap\enduser\winstore\servicescommon\lib\servicemain.cpp`

## pseudocode

```c
__int64 __fastcall ServiceControlHandler(DWORD dwControl, DWORD dwEventType, _QWORD *lpEventData, char *lpContext)
{
  DWORD v5; // ecx
  DWORD v6; // ecx
  SERVICE_STATUS_HANDLE v8; // rcx
  const char *v9; // r9
  void *v10; // rcx
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = dwControl - 1;
  if ( v5 )
  {
    v6 = v5 - 3;
    if ( v6 )
    {
      if ( v6 != 29 )
        return 120;
      if ( dwEventType == 5 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)lpContext + 10) + 56LL))(
          *((_QWORD *)lpContext + 10),
          *((unsigned int *)lpEventData + 1),
          lpEventData[1]);
      }
      else if ( dwEventType == 6 )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)lpContext + 10) + 64LL))(
          *((_QWORD *)lpContext + 10),
          *((unsigned int *)lpEventData + 1),
          lpEventData[1]);
      }
    }
    return 0;
  }
  v8 = (SERVICE_STATUS_HANDLE)*((_QWORD *)lpContext + 9);
  ++*((_DWORD *)lpContext + 15);
  *((_DWORD *)lpContext + 11) = 3;
  *(_QWORD *)(lpContext + 52) = 0;
  *((_DWORD *)lpContext + 16) = 1000;
  if ( SetServiceStatus(v8, (LPSERVICE_STATUS)(lpContext + 40))
    || (int)wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xC7,
              (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\servicemain.cpp",
              v9) >= 0 )
  {
    v10 = (void *)*((_QWORD *)lpContext + 3);
    if ( v10 )
    {
      lpContext[21] = 1;
      if ( !SetEvent(v10) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v11);
    }
    return 0;
  }
  return 1066;
}

```

## disassembly

```asm
0x1800211d0  push    rbx
0x1800211d2  sub     rsp, 20h
0x1800211d6  mov     rbx, r9
0x1800211d9  mov     r9, r8
0x1800211dc  sub     ecx, 1
0x1800211df  jz      short loc_180021229
0x1800211e1  sub     ecx, 3
0x1800211e4  jz      short loc_180021221
0x1800211e6  cmp     ecx, 1Dh
0x1800211e9  jz      short loc_1800211F2
0x1800211eb  mov     eax, 78h ; 'x'
0x1800211f0  jmp     short loc_180021223
0x1800211f2  cmp     edx, 5
0x1800211f5  jnz     short loc_180021204
0x1800211f7  mov     rcx, [rbx+50h]
0x1800211fb  mov     rax, [rcx]
0x1800211fe  mov     rax, [rax+38h]
0x180021202  jmp     short loc_180021214
0x180021204  cmp     edx, 6
0x180021207  jnz     short loc_180021221
0x180021209  mov     rcx, [rbx+50h]
0x18002120d  mov     rax, [rcx]
0x180021210  mov     rax, [rax+40h]
0x180021214  mov     edx, [r9+4]
0x180021218  mov     r8, [r8+8]
0x18002121c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021221  xor     eax, eax
0x180021223  add     rsp, 20h
0x180021227  pop     rbx
0x180021228  retn
0x180021229  mov     rcx, [rbx+48h]; hServiceStatus
0x18002122d  lea     rdx, [rbx+28h]; lpServiceStatus
0x180021231  inc     dword ptr [rbx+3Ch]
0x180021234  mov     dword ptr [rdx+4], 3
0x18002123b  mov     qword ptr [rbx+34h], 0
0x180021243  mov     dword ptr [rbx+40h], 3E8h
0x18002124a  call    cs:__imp_SetServiceStatus
0x180021250  test    eax, eax
0x180021252  jnz     short loc_180021275
0x180021254  mov     rcx, [rsp+28h]; this
0x180021259  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\services"...
0x180021260  mov     edx, 0C7h; void *
0x180021265  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002126a  test    eax, eax
0x18002126c  jns     short loc_180021275
0x18002126e  mov     eax, 42Ah
0x180021273  jmp     short loc_180021223
0x180021275  mov     rcx, [rbx+18h]; hEvent
0x180021279  test    rcx, rcx
0x18002127c  jz      short loc_180021221
0x18002127e  mov     byte ptr [rbx+15h], 1
0x180021282  call    cs:__imp_SetEvent
0x180021288  test    eax, eax
0x18002128a  jnz     short loc_180021221
0x18002128c  mov     rcx, [rsp+28h]; this
0x180021291  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021298  mov     edx, 0A01h; void *
0x18002129d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
