# ADM_GUID_MAP::~ADM_GUID_MAP(void)

- ea: `0x18000313c`
- end: `0x1800031ec`
- name: `??1ADM_GUID_MAP@@QEAA@XZ`
- size: `176`
- prototype: `void __fastcall(ADM_GUID_MAP *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003090`
- `0x18000333c`
- `0x180003f60`
- `0x1800043d0`

## callees

- `0x180001124`
- `0x18000313c`
- `0x1800031f4`
- `0x180003d54`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003197`
- `KERNEL32!EnterCriticalSection` at `0x180003197`
- `KERNEL32!LeaveCriticalSection` at `0x1800031bd`
- `KERNEL32!LeaveCriticalSection` at `0x1800031bd`
- `KERNEL32!DeleteCriticalSection` at `0x1800031cd`
- `KERNEL32!DeleteCriticalSection` at `0x1800031cd`

## pseudocode

```c
void __fastcall ADM_GUID_MAP::~ADM_GUID_MAP(ADM_GUID_MAP *this)
{
  volatile signed __int32 *v2; // rax
  volatile signed __int32 *v3; // rbx
  ADM_GUID_MAP *v4; // rdx
  ADM_GUID_MAP **v5; // rax

  v2 = (volatile signed __int32 *)ADM_SECURE_DATA::FindAndReferenceClientSecureData(this);
  v3 = v2;
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 6, 0xFFFFFFFF) == 1 )
    {
      ADM_SECURE_DATA::~ADM_SECURE_DATA((ADM_SECURE_DATA *)v2);
      operator delete((void *)v3);
    }
    if ( _InterlockedExchangeAdd(v3 + 6, 0xFFFFFFFF) == 1 )
    {
      ADM_SECURE_DATA::~ADM_SECURE_DATA((ADM_SECURE_DATA *)v3);
      operator delete((void *)v3);
    }
  }
  EnterCriticalSection(&ADM_GUID_MAP::sm_GuidMapDataLock);
  v4 = *(ADM_GUID_MAP **)this;
  if ( *(ADM_GUID_MAP **)(*(_QWORD *)this + 8LL) != this || (v5 = (ADM_GUID_MAP **)*((_QWORD *)this + 1), *v5 != this) )
    __fastfail(3u);
  *v5 = v4;
  *((_QWORD *)v4 + 1) = v5;
  LeaveCriticalSection(&ADM_GUID_MAP::sm_GuidMapDataLock);
  if ( *((_DWORD *)this + 18) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *((_DWORD *)this + 18) = 0;
  }
}

```

## disassembly

```asm
0x18000313c  mov     [rsp+arg_8], rbx
0x180003141  push    rdi
0x180003142  sub     rsp, 20h
0x180003146  mov     rdi, rcx
0x180003149  call    ?FindAndReferenceClientSecureData@ADM_SECURE_DATA@@SAPEAV1@PEAVADM_GUID_MAP@@@Z; ADM_SECURE_DATA::FindAndReferenceClientSecureData(ADM_GUID_MAP *)
0x18000314e  mov     rbx, rax
0x180003151  test    rax, rax
0x180003154  jz      short loc_180003190
0x180003156  or      edx, 0FFFFFFFFh
0x180003159  lock xadd [rax+18h], edx
0x18000315e  cmp     edx, 1
0x180003161  jnz     short loc_180003173
0x180003163  mov     rcx, rax; this
0x180003166  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x18000316b  mov     rcx, rbx; Block
0x18000316e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003173  or      eax, 0FFFFFFFFh
0x180003176  lock xadd [rbx+18h], eax
0x18000317b  cmp     eax, 1
0x18000317e  jnz     short loc_180003190
0x180003180  mov     rcx, rbx; this
0x180003183  call    ??1ADM_SECURE_DATA@@QEAA@XZ; ADM_SECURE_DATA::~ADM_SECURE_DATA(void)
0x180003188  mov     rcx, rbx; Block
0x18000318b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003190  lea     rcx, ?sm_GuidMapDataLock@ADM_GUID_MAP@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003197  call    cs:__imp_EnterCriticalSection
0x18000319d  mov     rdx, [rdi]
0x1800031a0  cmp     [rdx+8], rdi
0x1800031a4  jnz     short loc_1800031E5
0x1800031a6  mov     rax, [rdi+8]
0x1800031aa  cmp     [rax], rdi
0x1800031ad  jnz     short loc_1800031E5
0x1800031af  mov     [rax], rdx
0x1800031b2  lea     rcx, ?sm_GuidMapDataLock@ADM_GUID_MAP@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800031b9  mov     [rdx+8], rax
0x1800031bd  call    cs:__imp_LeaveCriticalSection
0x1800031c3  cmp     dword ptr [rdi+48h], 0
0x1800031c7  jz      short loc_1800031DA
0x1800031c9  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800031cd  call    cs:__imp_DeleteCriticalSection
0x1800031d3  mov     dword ptr [rdi+48h], 0
0x1800031da  mov     rbx, [rsp+28h+arg_8]
0x1800031df  add     rsp, 20h
0x1800031e3  pop     rdi
0x1800031e4  retn
0x1800031e5  mov     ecx, 3
0x1800031ea  int     29h; Win8: RtlFailFast(ecx)
```
