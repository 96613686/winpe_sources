# ADM_SECURE_DATA::~ADM_SECURE_DATA(void)

- ea: `0x1800031f4`
- end: `0x18000328f`
- name: `??1ADM_SECURE_DATA@@QEAA@XZ`
- size: `155`
- prototype: `void __fastcall(ADM_SECURE_DATA *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ce0`
- `0x180001f30`
- `0x1800020f0`
- `0x180002170`
- `0x180002240`
- `0x1800022e0`
- `0x1800025f0`
- `0x180002850`
- `0x180002a3c`
- `0x180002c40`
- `0x180002e90`
- `0x180003090`
- `0x18000313c`
- `0x18000340c`
- `0x180004468`

## callees

- `0x1800031f4`
- `0x180003298`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000320f`
- `KERNEL32!EnterCriticalSection` at `0x180003237`
- `KERNEL32!EnterCriticalSection` at `0x18000320f`
- `KERNEL32!EnterCriticalSection` at `0x180003237`
- `KERNEL32!LeaveCriticalSection` at `0x18000325d`
- `KERNEL32!LeaveCriticalSection` at `0x18000325d`
- `KERNEL32!DeleteCriticalSection` at `0x18000326d`
- `KERNEL32!DeleteCriticalSection` at `0x18000326d`

## pseudocode

```c
void __fastcall ADM_SECURE_DATA::~ADM_SECURE_DATA(ADM_SECURE_DATA *this)
{
  ADM_SECURE_DATA *v2; // rdx
  ADM_SECURE_DATA **v3; // rax
  struct _RTL_CRITICAL_SECTION *v4; // rcx

  ADM_SECURE_DATA::CleanupCryptoData(this);
  if ( *((_DWORD *)this + 31) )
  {
    EnterCriticalSection(&ADM_SECURE_DATA::sm_ServerSecureDataLock);
    v2 = *(ADM_SECURE_DATA **)this;
    if ( *(ADM_SECURE_DATA **)(*(_QWORD *)this + 8LL) == this )
    {
      v3 = (ADM_SECURE_DATA **)*((_QWORD *)this + 1);
      if ( *v3 == this )
      {
        v4 = &ADM_SECURE_DATA::sm_ServerSecureDataLock;
        goto LABEL_8;
      }
    }
LABEL_11:
    __fastfail(3u);
  }
  EnterCriticalSection(&ADM_SECURE_DATA::sm_ClientSecureDataLock);
  v2 = *(ADM_SECURE_DATA **)this;
  if ( *(ADM_SECURE_DATA **)(*(_QWORD *)this + 8LL) != this )
    goto LABEL_11;
  v3 = (ADM_SECURE_DATA **)*((_QWORD *)this + 1);
  if ( *v3 != this )
    goto LABEL_11;
  v4 = &ADM_SECURE_DATA::sm_ClientSecureDataLock;
LABEL_8:
  *v3 = v2;
  *((_QWORD *)v2 + 1) = v3;
  LeaveCriticalSection(v4);
  if ( *((_DWORD *)this + 26) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    *((_DWORD *)this + 26) = 0;
  }
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x1800031f4  push    rbx
0x1800031f6  sub     rsp, 20h
0x1800031fa  mov     rbx, rcx
0x1800031fd  call    ?CleanupCryptoData@ADM_SECURE_DATA@@AEAAXXZ; ADM_SECURE_DATA::CleanupCryptoData(void)
0x180003202  cmp     dword ptr [rbx+7Ch], 0
0x180003206  jz      short loc_180003230
0x180003208  lea     rcx, ?sm_ServerSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000320f  call    cs:__imp_EnterCriticalSection
0x180003215  mov     rdx, [rbx]
0x180003218  cmp     [rdx+8], rbx
0x18000321c  jnz     short loc_180003288
0x18000321e  mov     rax, [rbx+8]
0x180003222  cmp     [rax], rbx
0x180003225  jnz     short loc_180003288
0x180003227  lea     rcx, ?sm_ServerSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION ADM_SECURE_DATA::sm_ServerSecureDataLock
0x18000322e  jmp     short loc_180003256
0x180003230  lea     rcx, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003237  call    cs:__imp_EnterCriticalSection
0x18000323d  mov     rdx, [rbx]
0x180003240  cmp     [rdx+8], rbx
0x180003244  jnz     short loc_180003288
0x180003246  mov     rax, [rbx+8]
0x18000324a  cmp     [rax], rbx
0x18000324d  jnz     short loc_180003288
0x18000324f  lea     rcx, ?sm_ClientSecureDataLock@ADM_SECURE_DATA@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003256  mov     [rax], rdx
0x180003259  mov     [rdx+8], rax
0x18000325d  call    cs:__imp_LeaveCriticalSection
0x180003263  cmp     dword ptr [rbx+68h], 0
0x180003267  jz      short loc_18000327A
0x180003269  lea     rcx, [rbx+40h]; lpCriticalSection
0x18000326d  call    cs:__imp_DeleteCriticalSection
0x180003273  mov     dword ptr [rbx+68h], 0
0x18000327a  mov     qword ptr [rbx+10h], 0
0x180003282  add     rsp, 20h
0x180003286  pop     rbx
0x180003287  retn
0x180003288  mov     ecx, 3
0x18000328d  int     29h; Win8: RtlFailFast(ecx)
```
