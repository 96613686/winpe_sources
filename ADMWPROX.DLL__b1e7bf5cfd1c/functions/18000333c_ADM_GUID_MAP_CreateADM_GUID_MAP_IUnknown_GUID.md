# ADM_GUID_MAP::CreateADM_GUID_MAP(IUnknown *,_GUID)

- ea: `0x18000333c`
- end: `0x180003404`
- name: `?CreateADM_GUID_MAP@ADM_GUID_MAP@@SAPEAV1@PEAUIUnknown@@U_GUID@@@Z`
- size: `200`
- prototype: `struct ADM_GUID_MAP *__fastcall(struct IUnknown *, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003f60`

## callees

- `0x180001124`
- `0x180001130`
- `0x18000313c`
- `0x18000333c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003389`
- `KERNEL32!EnterCriticalSection` at `0x180003389`
- `KERNEL32!LeaveCriticalSection` at `0x1800033c1`
- `KERNEL32!LeaveCriticalSection` at `0x1800033c1`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800033d0`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x1800033d0`

## pseudocode

```c
struct ADM_GUID_MAP *__fastcall ADM_GUID_MAP::CreateADM_GUID_MAP(struct IUnknown *a1, struct _GUID *a2)
{
  char *v4; // rax
  char *v5; // rbx
  __int128 v6; // xmm0
  ADM_GUID_MAP *v7; // rax

  v4 = (char *)operator new(0x60u);
  v5 = v4;
  if ( !v4 )
    return 0;
  v6 = (__int128)*a2;
  *((_QWORD *)v4 + 2) = a1;
  *((_DWORD *)v4 + 6) = 1;
  *((_DWORD *)v4 + 18) = 0;
  *(_OWORD *)(v4 + 76) = v6;
  EnterCriticalSection(&ADM_GUID_MAP::sm_GuidMapDataLock);
  v7 = ADM_GUID_MAP::sm_GuidMapListHead;
  if ( *((ADM_GUID_MAP ***)ADM_GUID_MAP::sm_GuidMapListHead + 1) != &ADM_GUID_MAP::sm_GuidMapListHead )
    __fastfail(3u);
  *((_QWORD *)v5 + 1) = &ADM_GUID_MAP::sm_GuidMapListHead;
  *(_QWORD *)v5 = v7;
  *((_QWORD *)v7 + 1) = v5;
  ADM_GUID_MAP::sm_GuidMapListHead = (ADM_GUID_MAP *)v5;
  LeaveCriticalSection(&ADM_GUID_MAP::sm_GuidMapDataLock);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v5 + 32), 0x3E8u) )
  {
    ADM_GUID_MAP::~ADM_GUID_MAP((ADM_GUID_MAP *)v5);
    operator delete(v5);
    return 0;
  }
  *((_DWORD *)v5 + 18) = 1;
  return (struct ADM_GUID_MAP *)v5;
}

```

## disassembly

```asm
0x18000333c  mov     [rsp+arg_0], rbx
0x180003341  mov     [rsp+arg_8], rsi
0x180003346  push    rdi
0x180003347  sub     rsp, 20h
0x18000334b  mov     rsi, rcx
0x18000334e  mov     rdi, rdx
0x180003351  mov     ecx, 60h ; '`'; Size
0x180003356  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000335b  mov     rbx, rax
0x18000335e  test    rax, rax
0x180003361  jz      loc_1800033EF
0x180003367  movaps  xmm0, xmmword ptr [rdi]
0x18000336a  lea     rcx, ?sm_GuidMapDataLock@ADM_GUID_MAP@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003371  mov     [rax+10h], rsi
0x180003375  mov     esi, 1
0x18000337a  mov     [rax+18h], esi
0x18000337d  mov     dword ptr [rax+48h], 0
0x180003384  movdqu  xmmword ptr [rax+4Ch], xmm0
0x180003389  call    cs:__imp_EnterCriticalSection
0x18000338f  mov     rax, cs:?sm_GuidMapListHead@ADM_GUID_MAP@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_GUID_MAP::sm_GuidMapListHead
0x180003396  lea     rcx, ?sm_GuidMapListHead@ADM_GUID_MAP@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_GUID_MAP::sm_GuidMapListHead
0x18000339d  cmp     [rax+8], rcx
0x1800033a1  jz      short loc_1800033A8
0x1800033a3  lea     ecx, [rsi+2]
0x1800033a6  int     29h; Win8: RtlFailFast(ecx)
0x1800033a8  mov     [rbx+8], rcx
0x1800033ac  lea     rcx, ?sm_GuidMapDataLock@ADM_GUID_MAP@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800033b3  mov     [rbx], rax
0x1800033b6  mov     [rax+8], rbx
0x1800033ba  mov     cs:?sm_GuidMapListHead@ADM_GUID_MAP@@0U_LIST_ENTRY@@A, rbx; _LIST_ENTRY ADM_GUID_MAP::sm_GuidMapListHead
0x1800033c1  call    cs:__imp_LeaveCriticalSection
0x1800033c7  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800033cb  mov     edx, 3E8h; dwSpinCount
0x1800033d0  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800033d6  test    eax, eax
0x1800033d8  jz      short loc_1800033DF
0x1800033da  mov     [rbx+48h], esi
0x1800033dd  jmp     short loc_1800033F1
0x1800033df  mov     rcx, rbx; this
0x1800033e2  call    ??1ADM_GUID_MAP@@QEAA@XZ; ADM_GUID_MAP::~ADM_GUID_MAP(void)
0x1800033e7  mov     rcx, rbx; Block
0x1800033ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800033ef  xor     ebx, ebx
0x1800033f1  mov     rsi, [rsp+28h+arg_8]
0x1800033f6  mov     rax, rbx
0x1800033f9  mov     rbx, [rsp+28h+arg_0]
0x1800033fe  add     rsp, 20h
0x180003402  pop     rdi
0x180003403  retn
```
