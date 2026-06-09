# ReportWarningEvent(ushort *,int,int,ushort const *)

- ea: `0x14002d448`
- end: `0x14002d5cd`
- name: `?ReportWarningEvent@@YAJPEAGHHPEBG@Z`
- size: `389`
- prototype: `int(unsigned __int16 *, int, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140008d40`

## callees

- `0x14002d448`
- `0x140046430`

## import_xrefs

- `msvcrt!_itow` at `0x14002d4a0`
- `msvcrt!_itow` at `0x14002d4b2`
- `msvcrt!_itow` at `0x14002d4c4`
- `msvcrt!_itow` at `0x14002d4a0`
- `msvcrt!_itow` at `0x14002d4b2`
- `msvcrt!_itow` at `0x14002d4c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002d48c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002d48c`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14002d5a1`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14002d5a1`

## pseudocode

```c
ULONG __fastcall ReportWarningEvent(unsigned __int16 *a1, int a2, int a3, const unsigned __int16 *a4)
{
  DWORD CurrentProcessId; // ebx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+20h] [rbp-E0h] BYREF
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v17; // [rsp+40h] [rbp-C0h]
  int v18; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+4Ch] [rbp-B4h]
  wchar_t *v20; // [rsp+50h] [rbp-B0h]
  int v21; // [rsp+58h] [rbp-A8h]
  int v22; // [rsp+5Ch] [rbp-A4h]
  wchar_t *v23; // [rsp+60h] [rbp-A0h]
  int v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+6Ch] [rbp-94h]
  const unsigned __int16 *v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+7Ch] [rbp-84h]
  wchar_t v29[16]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[104]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v31[104]; // [rsp+170h] [rbp+70h] BYREF

  EventDescriptor = (EVENT_DESCRIPTOR)WBEM_MC_WBEM_HOST_KILLED;
  CurrentProcessId = GetCurrentProcessId();
  _itow(a2, Buffer, 10);
  _itow(a3, v31, 10);
  _itow(CurrentProcessId, v29, 10);
  v9 = -1;
  UserData.Ptr = (ULONGLONG)a1;
  v10 = -1;
  do
    ++v10;
  while ( a1[v10] );
  UserData.Reserved = 0;
  UserData.Size = 2 * v10 + 2;
  v17 = Buffer;
  v11 = -1;
  do
    ++v11;
  while ( Buffer[v11] );
  v19 = 0;
  v18 = 2 * v11 + 2;
  v20 = v31;
  v12 = -1;
  do
    ++v12;
  while ( v31[v12] );
  v22 = 0;
  v21 = 2 * v12 + 2;
  v23 = v29;
  v13 = -1;
  do
    ++v13;
  while ( v29[v13] );
  v25 = 0;
  v24 = 2 * v13 + 2;
  v26 = a4;
  do
    ++v9;
  while ( a4[v9] );
  v28 = 0;
  v27 = 2 * v9 + 2;
  return EventWrite(ProviderSubSystem_Globals::s_NtEventLogSource, &EventDescriptor, 5u, &UserData);
}

```

## disassembly

```asm
0x14002d448  mov     [rsp-8+arg_0], rbx
0x14002d44d  push    rbp
0x14002d44e  push    rsi
0x14002d44f  push    rdi
0x14002d450  push    r14
0x14002d452  push    r15
0x14002d454  lea     rbp, [rsp-150h]
0x14002d45c  sub     rsp, 250h
0x14002d463  mov     rax, cs:__security_cookie
0x14002d46a  xor     rax, rsp
0x14002d46d  mov     [rbp+170h+var_30], rax
0x14002d474  movups  xmm0, cs:WBEM_MC_WBEM_HOST_KILLED
0x14002d47b  mov     r14, r9
0x14002d47e  mov     esi, r8d
0x14002d481  mov     edi, edx
0x14002d483  mov     r15, rcx
0x14002d486  movdqu  xmmword ptr [rsp+270h+EventDescriptor.Id], xmm0
0x14002d48c  call    cs:__imp_GetCurrentProcessId
0x14002d492  mov     r8d, 0Ah; Radix
0x14002d498  lea     rdx, [rbp+170h+Buffer]; Buffer
0x14002d49c  mov     ecx, edi; Value
0x14002d49e  mov     ebx, eax
0x14002d4a0  call    cs:__imp__itow
0x14002d4a6  mov     r8d, 0Ah; Radix
0x14002d4ac  lea     rdx, [rbp+170h+var_100]; Buffer
0x14002d4b0  mov     ecx, esi; Value
0x14002d4b2  call    cs:__imp__itow
0x14002d4b8  mov     r8d, 0Ah; Radix
0x14002d4be  lea     rdx, [rbp+170h+var_1F0]; Buffer
0x14002d4c2  mov     ecx, ebx; Value
0x14002d4c4  call    cs:__imp__itow
0x14002d4ca  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14002d4ce  mov     [rsp+270h+UserData.Ptr], r15
0x14002d4d3  mov     rax, rcx
0x14002d4d6  xor     edx, edx
0x14002d4d8  inc     rax
0x14002d4db  cmp     [r15+rax*2], dx
0x14002d4e0  jnz     short loc_14002D4D8
0x14002d4e2  lea     eax, ds:2[rax*2]
0x14002d4e9  mov     dword ptr [rsp+270h+UserData.0Ch], edx
0x14002d4ed  mov     [rsp+270h+UserData.Size], eax
0x14002d4f1  lea     r8, [rbp+170h+Buffer]
0x14002d4f5  lea     rax, [rbp+170h+Buffer]
0x14002d4f9  mov     [rsp+270h+var_230], rax
0x14002d4fe  mov     rax, rcx
0x14002d501  inc     rax
0x14002d504  cmp     [r8+rax*2], dx
0x14002d509  jnz     short loc_14002D501
0x14002d50b  lea     eax, ds:2[rax*2]
0x14002d512  mov     [rsp+270h+var_224], edx
0x14002d516  mov     [rsp+270h+var_228], eax
0x14002d51a  lea     r8, [rbp+170h+var_100]
0x14002d51e  lea     rax, [rbp+170h+var_100]
0x14002d522  mov     [rsp+270h+var_220], rax
0x14002d527  mov     rax, rcx
0x14002d52a  inc     rax
0x14002d52d  cmp     [r8+rax*2], dx
0x14002d532  jnz     short loc_14002D52A
0x14002d534  lea     eax, ds:2[rax*2]
0x14002d53b  mov     [rsp+270h+var_214], edx
0x14002d53f  mov     [rsp+270h+var_218], eax
0x14002d543  lea     r8, [rbp+170h+var_1F0]
0x14002d547  lea     rax, [rbp+170h+var_1F0]
0x14002d54b  mov     [rsp+270h+var_210], rax
0x14002d550  mov     rax, rcx
0x14002d553  inc     rax
0x14002d556  cmp     [r8+rax*2], dx
0x14002d55b  jnz     short loc_14002D553
0x14002d55d  lea     eax, ds:2[rax*2]
0x14002d564  mov     [rsp+270h+var_204], edx
0x14002d568  mov     [rsp+270h+var_208], eax
0x14002d56c  mov     [rsp+270h+var_200], r14
0x14002d571  inc     rcx
0x14002d574  cmp     [r14+rcx*2], dx
0x14002d579  jnz     short loc_14002D571
0x14002d57b  lea     eax, ds:2[rcx*2]
0x14002d582  mov     [rsp+270h+var_1F4], edx
0x14002d586  mov     rcx, cs:?s_NtEventLogSource@ProviderSubSystem_Globals@@2_KA; RegHandle
0x14002d58d  lea     rdx, [rsp+270h+EventDescriptor]; EventDescriptor
0x14002d592  lea     r9, [rsp+270h+UserData]; UserData
0x14002d597  mov     [rsp+270h+var_1F8], eax
0x14002d59b  mov     r8d, 5; UserDataCount
0x14002d5a1  call    cs:__imp_EventWrite
0x14002d5a7  mov     rcx, [rbp+170h+var_30]
0x14002d5ae  xor     rcx, rsp; StackCookie
0x14002d5b1  call    __security_check_cookie
0x14002d5b6  mov     rbx, [rsp+270h+arg_0]
0x14002d5be  add     rsp, 250h
0x14002d5c5  pop     r15
0x14002d5c7  pop     r14
0x14002d5c9  pop     rdi
0x14002d5ca  pop     rsi
0x14002d5cb  pop     rbp
0x14002d5cc  retn
```
