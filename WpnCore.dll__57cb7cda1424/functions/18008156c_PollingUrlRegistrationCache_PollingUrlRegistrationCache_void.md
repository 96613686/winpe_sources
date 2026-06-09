# PollingUrlRegistrationCache::~PollingUrlRegistrationCache(void)

- ea: `0x18008156c`
- end: `0x18008162c`
- name: `??1PollingUrlRegistrationCache@@UEAA@XZ`
- size: `192`
- prototype: `void __fastcall(PollingUrlRegistrationCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180081530`

## callees

- `0x18008156c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081603`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081603`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081611`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081611`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800815b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800815c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800815ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800815b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800815c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800815ed`

## pseudocode

```c
void __fastcall PollingUrlRegistrationCache::~PollingUrlRegistrationCache(PollingUrlRegistrationCache *this)
{
  void **v1; // rsi
  void ***v2; // rbx
  void **v3; // rax
  void **v4; // rcx
  void **v5; // rcx
  __int64 i; // rdi
  void **v7; // rcx
  HANDLE ProcessHeap; // rax

  *(_QWORD *)this = &PollingUrlRegistrationCache::`vftable';
  v1 = (void **)((char *)this + 8);
  while ( 1 )
  {
    v2 = (void ***)*v1;
    if ( *v1 == v1 )
      break;
    if ( v2[1] != v1 || (v3 = *v2, (*v2)[1] != v2) )
      __fastfail(3u);
    *v1 = v3;
    v3[1] = v1;
    v4 = v2[2];
    if ( v4 )
    {
      CoTaskMemFree(v4);
      v2[2] = 0;
    }
    v5 = v2[13];
    if ( v5 )
    {
      CoTaskMemFree(v5);
      v2[13] = 0;
    }
    for ( i = 0; (unsigned int)i < *((_DWORD *)v2 + 10); i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= 5 )
        break;
      v7 = v2[i + 6];
      if ( v7 )
      {
        CoTaskMemFree(v7);
        v2[i + 6] = 0;
      }
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
}

```

## disassembly

```asm
0x18008156c  push    rbx
0x18008156e  push    rbp
0x18008156f  push    rsi
0x180081570  push    rdi
0x180081571  sub     rsp, 28h
0x180081575  lea     rax, ??_7PollingUrlRegistrationCache@@6B@; const PollingUrlRegistrationCache::`vftable'
0x18008157c  mov     [rcx], rax
0x18008157f  lea     rsi, [rcx+8]
0x180081583  mov     rbx, [rsi]
0x180081586  cmp     rbx, rsi
0x180081589  jz      loc_180081623
0x18008158f  cmp     [rbx+8], rsi
0x180081593  jnz     loc_18008161C
0x180081599  mov     rax, [rbx]
0x18008159c  cmp     [rax+8], rbx
0x1800815a0  jnz     short loc_18008161C
0x1800815a2  mov     [rsi], rax
0x1800815a5  mov     [rax+8], rsi
0x1800815a9  mov     rcx, [rbx+10h]; pv
0x1800815ad  test    rcx, rcx
0x1800815b0  jz      short loc_1800815C0
0x1800815b2  call    cs:__imp_CoTaskMemFree
0x1800815b8  mov     qword ptr [rbx+10h], 0
0x1800815c0  mov     rcx, [rbx+68h]; pv
0x1800815c4  test    rcx, rcx
0x1800815c7  jz      short loc_1800815D7
0x1800815c9  call    cs:__imp_CoTaskMemFree
0x1800815cf  mov     qword ptr [rbx+68h], 0
0x1800815d7  xor     edi, edi
0x1800815d9  cmp     [rbx+28h], edi
0x1800815dc  jbe     short loc_180081603
0x1800815de  cmp     edi, 5
0x1800815e1  jnb     short loc_180081603
0x1800815e3  mov     rcx, [rbx+rdi*8+30h]; pv
0x1800815e8  test    rcx, rcx
0x1800815eb  jz      short loc_1800815FC
0x1800815ed  call    cs:__imp_CoTaskMemFree
0x1800815f3  mov     qword ptr [rbx+rdi*8+30h], 0
0x1800815fc  inc     edi
0x1800815fe  cmp     edi, [rbx+28h]
0x180081601  jb      short loc_1800815DE
0x180081603  call    cs:__imp_GetProcessHeap
0x180081609  mov     r8, rbx; lpMem
0x18008160c  xor     edx, edx; dwFlags
0x18008160e  mov     rcx, rax; hHeap
0x180081611  call    cs:__imp_HeapFree
0x180081617  jmp     loc_180081583
0x18008161c  mov     ecx, 3
0x180081621  int     29h; Win8: RtlFailFast(ecx)
0x180081623  add     rsp, 28h
0x180081627  pop     rdi
0x180081628  pop     rsi
0x180081629  pop     rbp
0x18008162a  pop     rbx
0x18008162b  retn
```
