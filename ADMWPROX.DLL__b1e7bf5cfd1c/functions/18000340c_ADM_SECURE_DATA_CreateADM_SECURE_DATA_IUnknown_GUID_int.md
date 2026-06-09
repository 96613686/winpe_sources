# ADM_SECURE_DATA::CreateADM_SECURE_DATA(IUnknown *,_GUID,int)

- ea: `0x18000340c`
- end: `0x18000352f`
- name: `?CreateADM_SECURE_DATA@ADM_SECURE_DATA@@SAPEAV1@PEAUIUnknown@@U_GUID@@H@Z`
- size: `291`
- prototype: `struct ADM_SECURE_DATA *__fastcall(struct IUnknown *, struct _GUID *__struct_ptr, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003e3c`
- `0x180003f60`

## callees

- `0x180001124`
- `0x180001130`
- `0x1800031f4`
- `0x18000340c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000347d`
- `KERNEL32!EnterCriticalSection` at `0x1800034b9`
- `KERNEL32!EnterCriticalSection` at `0x18000347d`
- `KERNEL32!EnterCriticalSection` at `0x1800034b9`
- `KERNEL32!LeaveCriticalSection` at `0x1800034f3`
- `KERNEL32!LeaveCriticalSection` at `0x1800034f3`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180003502`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180003502`

## pseudocode

```c
struct ADM_SECURE_DATA *__fastcall ADM_SECURE_DATA::CreateADM_SECURE_DATA(
        struct IUnknown *a1,
        struct _GUID *a2,
        int a3)
{
  char *v6; // rax
  char *v7; // rbx
  __int128 v8; // xmm0
  ADM_SECURE_DATA *v9; // rax
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  ADM_SECURE_DATA *v11; // rax

  v6 = (char *)operator new(0x80u);
  v7 = v6;
  if ( !v6 )
    return 0;
  v8 = (__int128)*a2;
  *((_QWORD *)v6 + 2) = a1;
  *((_DWORD *)v6 + 6) = 1;
  *((_QWORD *)v6 + 4) = 0;
  *((_QWORD *)v6 + 5) = 0;
  *((_QWORD *)v6 + 6) = 0;
  *((_QWORD *)v6 + 7) = 0;
  *((_DWORD *)v6 + 26) = 0;
  *((_DWORD *)v6 + 31) = a3;
  *(_OWORD *)(v6 + 108) = v8;
  if ( a3 )
  {
    EnterCriticalSection(&ADM_SECURE_DATA::sm_ServerSecureDataLock);
    v9 = ADM_SECURE_DATA::sm_ServerSecureDataListHead;
    if ( *((ADM_SECURE_DATA ***)ADM_SECURE_DATA::sm_ServerSecureDataListHead + 1) == &ADM_SECURE_DATA::sm_ServerSecureDataListHead )
    {
      *((_QWORD *)v7 + 1) = &ADM_SECURE_DATA::sm_ServerSecureDataListHead;
      v10 = &ADM_SECURE_DATA::sm_ServerSecureDataLock;
      *(_QWORD *)v7 = v9;
      *((_QWORD *)v9 + 1) = v7;
      ADM_SECURE_DATA::sm_ServerSecureDataListHead = (ADM_SECURE_DATA *)v7;
      goto LABEL_8;
    }
LABEL_6:
    __fastfail(3u);
  }
  EnterCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
  v11 = ADM_SECURE_DATA::sm_ClientSecureDataListHead;
  if ( *((ADM_SECURE_DATA ***)ADM_SECURE_DATA::sm_ClientSecureDataListHead + 1) != &ADM_SECURE_DATA::sm_ClientSecureDataListHead )
    goto LABEL_6;
  *((_QWORD *)v7 + 1) = &ADM_SECURE_DATA::sm_ClientSecureDataListHead;
  v10 = &ADM_SECURE_DATA::sm_ClientSecureDataLock;
  *(_QWORD *)v7 = v11;
  *((_QWORD *)v11 + 1) = v7;
  ADM_SECURE_DATA::sm_ClientSecureDataListHead = (ADM_SECURE_DATA *)v7;
LABEL_8:
  LeaveCriticalSection(v10);
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v7 + 64), 0x3E8u) )
  {
    ADM_SECURE_DATA::~ADM_SECURE_DATA((ADM_SECURE_DATA *)v7);
    operator delete(v7);
    return 0;
  }
  *((_DWORD *)v7 + 26) = 1;
  return (struct ADM_SECURE_DATA *)v7;
}

```

## disassembly

```asm
0x18000340c  push    rbx
0x18000340e  push    rbp
0x18000340f  push    rsi
0x180003410  push    rdi
0x180003411  sub     rsp, 28h
0x180003415  mov     rbp, rcx
0x180003418  mov     edi, r8d
0x18000341b  mov     ecx, 80h; Size
0x180003420  mov     rsi, rdx
0x180003423  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003428  mov     rbx, rax
0x18000342b  test    rax, rax
0x18000342e  jz      loc_180003521
0x180003434  movaps  xmm0, xmmword ptr [rsi]
0x180003437  mov     [rax+10h], rbp
0x18000343b  mov     ebp, 1
0x180003440  mov     [rax+18h], ebp
0x180003443  mov     qword ptr [rax+20h], 0
0x18000344b  mov     qword ptr [rax+28h], 0
0x180003453  mov     qword ptr [rax+30h], 0
0x18000345b  mov     qword ptr [rax+38h], 0
0x180003463  mov     dword ptr [rax+68h], 0
0x18000346a  mov     [rax+7Ch], edi
0x18000346d  movdqu  xmmword ptr [rax+6Ch], xmm0
0x180003472  test    edi, edi
0x180003474  jz      short loc_1800034B2
0x180003476  lea     rcx, ?sm_ServerSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000347d  call    cs:__imp_EnterCriticalSection
0x180003483  mov     rax, cs:?sm_ServerSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ServerSecureDataListHead
0x18000348a  lea     rcx, ?sm_ServerSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ServerSecureDataListHead
0x180003491  cmp     [rax+8], rcx
0x180003495  jnz     short loc_1800034D3
0x180003497  mov     [rbx+8], rcx
0x18000349b  lea     rcx, ?sm_ServerSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ADM_SECURE_DATA::sm_ServerSecureDataLock
0x1800034a2  mov     [rbx], rax
0x1800034a5  mov     [rax+8], rbx
0x1800034a9  mov     cs:?sm_ServerSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A, rbx; _LIST_ENTRY ADM_SECURE_DATA::sm_ServerSecureDataListHead
0x1800034b0  jmp     short loc_1800034F3
0x1800034b2  lea     rcx, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800034b9  call    cs:__imp_EnterCriticalSection
0x1800034bf  mov     rax, cs:?sm_ClientSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ClientSecureDataListHead
0x1800034c6  lea     rcx, ?sm_ClientSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A; _LIST_ENTRY ADM_SECURE_DATA::sm_ClientSecureDataListHead
0x1800034cd  cmp     [rax+8], rcx
0x1800034d1  jz      short loc_1800034DA
0x1800034d3  mov     ecx, 3
0x1800034d8  int     29h; Win8: RtlFailFast(ecx)
0x1800034da  mov     [rbx+8], rcx
0x1800034de  lea     rcx, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800034e5  mov     [rbx], rax
0x1800034e8  mov     [rax+8], rbx
0x1800034ec  mov     cs:?sm_ClientSecureDataListHead@ADM_SECURE_DATA@@0U_LIST_ENTRY@@A, rbx; _LIST_ENTRY ADM_SECURE_DATA::sm_ClientSecureDataListHead
0x1800034f3  call    cs:__imp_LeaveCriticalSection
0x1800034f9  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800034fd  mov     edx, 3E8h; dwSpinCount
0x180003502  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180003508  test    eax, eax
0x18000350a  jz      short loc_180003511
0x18000350c  mov     [rbx+68h], ebp
0x18000350f  jmp     short loc_180003523
0x180003511  mov     rcx, rbx; this
0x180003514  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x180003519  mov     rcx, rbx; Block
0x18000351c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003521  xor     ebx, ebx
0x180003523  mov     rax, rbx
0x180003526  add     rsp, 28h
0x18000352a  pop     rdi
0x18000352b  pop     rsi
0x18000352c  pop     rbp
0x18000352d  pop     rbx
0x18000352e  retn
```
