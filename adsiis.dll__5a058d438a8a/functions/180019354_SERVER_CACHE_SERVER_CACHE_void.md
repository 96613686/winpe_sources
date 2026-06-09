# SERVER_CACHE::~SERVER_CACHE(void)

- ea: `0x180019354`
- end: `0x1800193ba`
- name: `??1SERVER_CACHE@@IEAA@XZ`
- size: `102`
- prototype: `void __fastcall(SERVER_CACHE *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x180001a28`
- `0x180002620`
- `0x180003aac`
- `0x18000cd44`
- `0x18000d3b0`
- `0x18000d524`
- `0x18000fee8`
- `0x1800147d8`

## callees

- `0x1800192e4`
- `0x180019354`
- `0x18001941c`

## pseudocode

```c
void __fastcall SERVER_CACHE::~SERVER_CACHE(SERVER_CACHE *this)
{
  int v2; // r8d
  __int64 v3; // rdx
  SERVER_CACHE_ITEM *v4; // rcx
  unsigned int v5; // edx
  __int64 v6; // rax

  *((_DWORD *)this + 4) = 0;
LABEL_2:
  v2 = *((_DWORD *)this + 2);
  while ( 1 )
  {
    v3 = *((int *)this + 4);
    if ( (int)v3 >= v2 )
      break;
    v4 = *(SERVER_CACHE_ITEM **)(*(_QWORD *)this + 8 * v3);
    v5 = v3 + 1;
    *((_DWORD *)this + 4) = v5;
    if ( v4 )
    {
      v6 = *(int *)v4;
      if ( (int)v6 >= 0 && (int)v6 < v2 )
      {
        --*((_DWORD *)this + 3);
        v5 = v6;
        *(_QWORD *)(*(_QWORD *)this + 8 * v6) = 0;
      }
      SERVER_CACHE_ITEM::`scalar deleting destructor'(v4, v5);
      goto LABEL_2;
    }
  }
  *((_DWORD *)this + 4) = 0;
  SIMPLE_DICT::~SIMPLE_DICT(this);
}

```

## disassembly

```asm
0x180019354  push    rbx
0x180019356  sub     rsp, 20h
0x18001935a  mov     rbx, rcx
0x18001935d  mov     dword ptr [rcx+10h], 0
0x180019364  mov     r8d, [rbx+8]
0x180019368  movsxd  rdx, dword ptr [rbx+10h]
0x18001936c  cmp     edx, r8d
0x18001936f  jge     short loc_1800193A6
0x180019371  mov     rax, [rbx]
0x180019374  mov     rcx, [rax+rdx*8]; this
0x180019378  inc     edx
0x18001937a  mov     [rbx+10h], edx
0x18001937d  test    rcx, rcx
0x180019380  jz      short loc_180019368
0x180019382  movsxd  rax, dword ptr [rcx]
0x180019385  test    eax, eax
0x180019387  js      short loc_18001939F
0x180019389  cmp     eax, r8d
0x18001938c  jge     short loc_18001939F
0x18001938e  dec     dword ptr [rbx+0Ch]
0x180019391  mov     rdx, rax; unsigned int
0x180019394  mov     rax, [rbx]
0x180019397  mov     qword ptr [rax+rdx*8], 0
0x18001939f  call    ??_GSERVER_CACHE_ITEM@@QEAAPEAXI@Z; SERVER_CACHE_ITEM::`scalar deleting destructor'(uint)
0x1800193a4  jmp     short loc_180019364
0x1800193a6  mov     rcx, rbx; this
0x1800193a9  mov     dword ptr [rbx+10h], 0
0x1800193b0  add     rsp, 20h
0x1800193b4  pop     rbx
0x1800193b5  jmp     ??1SIMPLE_DICT@@QEAA@XZ; SIMPLE_DICT::~SIMPLE_DICT(void)
```
