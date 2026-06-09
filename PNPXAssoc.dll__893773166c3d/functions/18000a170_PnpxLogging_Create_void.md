# PnpxLogging::Create(void)

- ea: `0x18000a170`
- end: `0x18000a283`
- name: `?Create@PnpxLogging@@IEAAXXZ`
- size: `275`
- prototype: `void __fastcall(PnpxLogging *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000af5c`

## callees

- `0x18000a170`
- `0x180012e00`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x18000a200`
- `KERNEL32!GetModuleHandleExW` at `0x18000a218`
- `KERNEL32!GetModuleHandleExW` at `0x18000a200`
- `KERNEL32!GetModuleHandleExW` at `0x18000a218`
- `KERNEL32!GetProcAddress` at `0x18000a22e`
- `KERNEL32!GetProcAddress` at `0x18000a22e`
- `KERNEL32!FreeLibrary` at `0x18000a251`
- `KERNEL32!FreeLibrary` at `0x18000a251`
- `ADVAPI32!EventRegister` at `0x18000a1d8`
- `ADVAPI32!EventRegister` at `0x18000a1d8`

## string_xrefs

- `0x18000a211`: `advapi32.dll`
- `0x18000a1eb`: `api-ms-win-eventing-provider-l1-1-0.dll`

## pseudocode

```c
void __fastcall PnpxLogging::Create(PnpxLogging *this)
{
  _QWORD *v1; // rdi
  _QWORD *v3; // rsi
  bool v4; // zf
  unsigned __int16 *v5; // rdi
  unsigned int v6; // ebp
  FARPROC ProcAddress; // rax
  __int64 v8; // rax
  HMODULE phModule; // [rsp+30h] [rbp-48h] BYREF
  GUID ProviderId; // [rsp+38h] [rbp-40h] BYREF

  v1 = (_QWORD *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 1) = v1;
  *((_BYTE *)this + 16) = 1;
  v3 = v1 + 4;
  v4 = v1[4] == 0;
  ProviderId = *(GUID *)(v1[1] - 16LL);
  if ( !v4 )
    __fastfail(5u);
  v1[5] = 0;
  v1[6] = 0;
  if ( !EventRegister(&ProviderId, tlgEnableCallback, v1, v1 + 4) )
  {
    v5 = (unsigned __int16 *)v1[1];
    phModule = 0;
    v6 = *v5;
    if ( GetModuleHandleExW(0, L"api-ms-win-eventing-provider-l1-1-0.dll", &phModule)
      || GetModuleHandleExW(0, L"advapi32.dll", &phModule) )
    {
      ProcAddress = GetProcAddress(phModule, "EventSetInformation");
      if ( ProcAddress )
        ((void (__fastcall *)(_QWORD, __int64, unsigned __int16 *, _QWORD))ProcAddress)(*v3, 2, v5, v6);
      FreeLibrary(phModule);
    }
  }
  v8 = *(_QWORD *)this;
  *((_DWORD *)this + 5) = 1;
  (*(void (__fastcall **)(PnpxLogging *))(v8 + 8))(this);
}

```

## disassembly

```asm
0x18000a170  push    rbx
0x18000a172  push    rbp
0x18000a173  push    rsi
0x18000a174  push    rdi
0x18000a175  sub     rsp, 58h
0x18000a179  mov     rax, cs:__security_cookie
0x18000a180  xor     rax, rsp
0x18000a183  mov     [rsp+78h+var_30], rax
0x18000a188  mov     rdi, [rcx+18h]
0x18000a18c  mov     rbx, rcx
0x18000a18f  mov     [rcx+8], rdi
0x18000a193  mov     byte ptr [rcx+10h], 1
0x18000a197  mov     rax, [rdi+8]
0x18000a19b  lea     rsi, [rdi+20h]
0x18000a19f  cmp     qword ptr [rsi], 0
0x18000a1a3  movups  xmm0, xmmword ptr [rax-10h]
0x18000a1a7  movdqu  xmmword ptr [rsp+78h+ProviderId.Data1], xmm0
0x18000a1ad  jz      short loc_18000A1B6
0x18000a1af  mov     ecx, 5
0x18000a1b4  int     29h; Win8: RtlFailFast(ecx)
0x18000a1b6  mov     r9, rsi; RegHandle
0x18000a1b9  mov     qword ptr [rdi+28h], 0
0x18000a1c1  mov     r8, rdi; CallbackContext
0x18000a1c4  mov     qword ptr [rdi+30h], 0
0x18000a1cc  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000a1d3  lea     rcx, [rsp+78h+ProviderId]; ProviderId
0x18000a1d8  call    cs:__imp_EventRegister
0x18000a1de  test    eax, eax
0x18000a1e0  jnz     short loc_18000A257
0x18000a1e2  mov     rdi, [rdi+8]
0x18000a1e6  lea     r8, [rsp+78h+phModule]; phModule
0x18000a1eb  lea     rdx, aApiMsWinEventi; "api-ms-win-eventing-provider-l1-1-0.dll"
0x18000a1f2  mov     [rsp+78h+phModule], 0
0x18000a1fb  xor     ecx, ecx; dwFlags
0x18000a1fd  movzx   ebp, word ptr [rdi]
0x18000a200  call    cs:__imp_GetModuleHandleExW
0x18000a206  test    eax, eax
0x18000a208  jnz     short loc_18000A222
0x18000a20a  lea     r8, [rsp+78h+phModule]; phModule
0x18000a20f  xor     ecx, ecx; dwFlags
0x18000a211  lea     rdx, LibFileName; "advapi32.dll"
0x18000a218  call    cs:__imp_GetModuleHandleExW
0x18000a21e  test    eax, eax
0x18000a220  jz      short loc_18000A257
0x18000a222  mov     rcx, [rsp+78h+phModule]; hModule
0x18000a227  lea     rdx, aEventsetinform; "EventSetInformation"
0x18000a22e  call    cs:__imp_GetProcAddress
0x18000a234  test    rax, rax
0x18000a237  jz      short loc_18000A24C
0x18000a239  mov     rcx, [rsi]
0x18000a23c  mov     r9d, ebp
0x18000a23f  mov     r8, rdi
0x18000a242  mov     edx, 2
0x18000a247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a24c  mov     rcx, [rsp+78h+phModule]; hLibModule
0x18000a251  call    cs:__imp_FreeLibrary
0x18000a257  mov     rax, [rbx]
0x18000a25a  mov     rcx, rbx
0x18000a25d  mov     dword ptr [rbx+14h], 1
0x18000a264  mov     rax, [rax+8]
0x18000a268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a26d  mov     rcx, [rsp+78h+var_30]
0x18000a272  xor     rcx, rsp; StackCookie
0x18000a275  call    __security_check_cookie
0x18000a27a  add     rsp, 58h
0x18000a27e  pop     rdi
0x18000a27f  pop     rsi
0x18000a280  pop     rbp
0x18000a281  pop     rbx
0x18000a282  retn
```
