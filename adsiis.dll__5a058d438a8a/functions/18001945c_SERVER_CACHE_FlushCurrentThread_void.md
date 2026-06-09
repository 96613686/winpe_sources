# SERVER_CACHE::FlushCurrentThread(void)

- ea: `0x18001945c`
- end: `0x1800194fb`
- name: `?FlushCurrentThread@SERVER_CACHE@@SAXXZ`
- size: `159`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800169d4`

## callees

- `0x180019304`
- `0x180019334`
- `0x18001941c`
- `0x18001945c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180019482`
- `KERNEL32!GetCurrentThreadId` at `0x180019482`

## pseudocode

```c
void __fastcall SERVER_CACHE::FlushCurrentThread(__int64 a1, struct WIN32_CRITSEC *a2)
{
  DWORD CurrentThreadId; // eax
  SERVER_CACHE *v3; // rbx
  DWORD v4; // edi
  int v5; // r8d
  __int64 v6; // rdx
  SERVER_CACHE_ITEM *v7; // rcx
  unsigned int v8; // edx
  __int64 v9; // rax
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  CLock::CLock((CLock *)&v10, a2);
  if ( v10 && SERVER_CACHE::sm_pServerCache )
  {
    CurrentThreadId = GetCurrentThreadId();
    v3 = SERVER_CACHE::sm_pServerCache;
    v4 = CurrentThreadId;
    *((_DWORD *)SERVER_CACHE::sm_pServerCache + 4) = 0;
LABEL_4:
    v5 = *((_DWORD *)v3 + 2);
    while ( 1 )
    {
      v6 = *((int *)v3 + 4);
      if ( (int)v6 >= v5 )
        break;
      v7 = *(SERVER_CACHE_ITEM **)(*(_QWORD *)v3 + 8 * v6);
      v8 = v6 + 1;
      *((_DWORD *)v3 + 4) = v8;
      if ( v7 )
      {
        if ( v4 == *((_DWORD *)v7 + 30) )
        {
          v9 = *(int *)v7;
          if ( (int)v9 >= 0 && (int)v9 < v5 )
          {
            --*((_DWORD *)v3 + 3);
            v8 = v9;
            *(_QWORD *)(*(_QWORD *)v3 + 8 * v9) = 0;
          }
          SERVER_CACHE_ITEM::`scalar deleting destructor'(v7, v8);
        }
        goto LABEL_4;
      }
    }
    *((_DWORD *)v3 + 4) = 0;
  }
  CLock::~CLock((CLock *)&v10);
}

```

## disassembly

```asm
0x18001945c  mov     [rsp+arg_8], rbx
0x180019461  push    rdi
0x180019462  sub     rsp, 20h
0x180019466  lea     rcx, [rsp+28h+arg_0]; this
0x18001946b  call    ??0CLock@@QEAA@PEAVWIN32_CRITSEC@@@Z; CLock::CLock(WIN32_CRITSEC *)
0x180019470  cmp     [rsp+28h+arg_0], 0
0x180019476  jz      short loc_1800194E6
0x180019478  cmp     cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA, 0; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x180019480  jz      short loc_1800194E6
0x180019482  call    cs:__imp_GetCurrentThreadId
0x180019488  mov     rbx, cs:?sm_pServerCache@SERVER_CACHE@@1PEAV1@EA; SERVER_CACHE * SERVER_CACHE::sm_pServerCache
0x18001948f  mov     edi, eax
0x180019491  mov     dword ptr [rbx+10h], 0
0x180019498  mov     r8d, [rbx+8]
0x18001949c  movsxd  rdx, dword ptr [rbx+10h]
0x1800194a0  cmp     edx, r8d
0x1800194a3  jge     short loc_1800194DF
0x1800194a5  mov     rax, [rbx]
0x1800194a8  mov     rcx, [rax+rdx*8]; this
0x1800194ac  inc     edx
0x1800194ae  mov     [rbx+10h], edx
0x1800194b1  test    rcx, rcx
0x1800194b4  jz      short loc_18001949C
0x1800194b6  cmp     edi, [rcx+78h]
0x1800194b9  jnz     short loc_180019498
0x1800194bb  movsxd  rax, dword ptr [rcx]
0x1800194be  test    eax, eax
0x1800194c0  js      short loc_1800194D8
0x1800194c2  cmp     eax, r8d
0x1800194c5  jge     short loc_1800194D8
0x1800194c7  dec     dword ptr [rbx+0Ch]
0x1800194ca  mov     rdx, rax; unsigned int
0x1800194cd  mov     rax, [rbx]
0x1800194d0  mov     qword ptr [rax+rdx*8], 0
0x1800194d8  call    ??_GSERVER_CACHE_ITEM@@QEAAPEAXI@Z; SERVER_CACHE_ITEM::`scalar deleting destructor'(uint)
0x1800194dd  jmp     short loc_180019498
0x1800194df  mov     dword ptr [rbx+10h], 0
0x1800194e6  lea     rcx, [rsp+28h+arg_0]; this
0x1800194eb  call    ??1CLock@@QEAA@XZ; CLock::~CLock(void)
0x1800194f0  mov     rbx, [rsp+28h+arg_8]
0x1800194f5  add     rsp, 20h
0x1800194f9  pop     rdi
0x1800194fa  retn
```
