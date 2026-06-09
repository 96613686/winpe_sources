# CMpeg2VersionFilteredPSIParse::PSICurSectionCompleted(long)

- ea: `0x180021200`
- end: `0x1800212e0`
- name: `?PSICurSectionCompleted@CMpeg2VersionFilteredPSIParse@@UEAAXJ@Z`
- size: `224`
- prototype: `void __fastcall(CMpeg2VersionFilteredPSIParse *__hidden this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001e6b0`
- `0x180021200`
- `0x1800219b4`
- `0x180021b04`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800212b0`
- `KERNEL32!LeaveCriticalSection` at `0x1800212b0`
- `KERNEL32!EnterCriticalSection` at `0x18002125a`
- `KERNEL32!EnterCriticalSection` at `0x18002125a`

## pseudocode

```c
void __fastcall CMpeg2VersionFilteredPSIParse::PSICurSectionCompleted(CMpeg2VersionFilteredPSIParse *this, int a2)
{
  char *v2; // rdi
  unsigned int v4; // ebp
  __int64 v5; // rbx
  char *v6; // rax
  char *i; // r8
  char *v8; // rdx
  char **v9; // rax
  char *v10; // r8
  _QWORD *v11; // rax
  __int64 v12; // r8

  v2 = (char *)this + 416;
  if ( a2 < 0 )
  {
    TGenericMap<unsigned long,unsigned long,0,5,19>::Clear(v2);
  }
  else
  {
    v4 = *((_DWORD *)this + 211);
    v5 = (*(unsigned int (__fastcall **)(char *, _QWORD))(*(_QWORD *)v2 + 8LL))(v2, v4) % 0x13;
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 384));
    v6 = &v2[16 * v5 + 64];
    for ( i = *(char **)v6; i != v6; i = *(char **)i )
    {
      v8 = i - 32;
      if ( *((_DWORD *)i - 8) == v4 )
      {
        if ( i != (char *)32 )
        {
          v9 = (char **)*((_QWORD *)v8 + 5);
          v10 = *(char **)i;
          *v9 = v10;
          *((_QWORD *)v10 + 1) = v9;
          v11 = (_QWORD *)*((_QWORD *)v8 + 3);
          v12 = *((_QWORD *)v8 + 2);
          *v11 = v12;
          *(_QWORD *)(v12 + 8) = v11;
          ObjectPool<TGenericMap<unsigned long,unsigned long,0,5,19>::TABLE_ENTRY,5>::Recycle(v2 + 8);
        }
        break;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 384));
    TGenericMap<unsigned long,unsigned long,0,5,19>::Store(
      v2,
      *((unsigned int *)this + 210),
      *((unsigned int *)this + 211));
  }
}

```

## disassembly

```asm
0x180021200  push    rbx
0x180021202  push    rbp
0x180021203  push    rsi
0x180021204  push    rdi
0x180021205  push    r14
0x180021207  sub     rsp, 20h
0x18002120b  lea     rdi, [rcx+1A0h]
0x180021212  mov     rsi, rcx
0x180021215  test    edx, edx
0x180021217  js      loc_1800212CD
0x18002121d  mov     ebp, [rcx+34Ch]
0x180021223  mov     edx, ebp
0x180021225  mov     rax, [rdi]
0x180021228  mov     rcx, rdi
0x18002122b  mov     rax, [rax+8]
0x18002122f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021234  mov     ecx, eax
0x180021236  lea     r14, [rdi+180h]
0x18002123d  mov     rax, 0D79435E50D79435Fh
0x180021247  mul     rcx
0x18002124a  shr     rdx, 4
0x18002124e  imul    rax, rdx, 13h
0x180021252  sub     rcx, rax
0x180021255  mov     ebx, ecx
0x180021257  mov     rcx, r14; lpCriticalSection
0x18002125a  call    cs:__imp_EnterCriticalSection
0x180021260  lea     rax, [rbx+4]
0x180021264  shl     rax, 4
0x180021268  add     rax, rdi
0x18002126b  mov     r8, [rax]
0x18002126e  jmp     short loc_18002127B
0x180021270  lea     rdx, [r8-20h]
0x180021274  cmp     [rdx], ebp
0x180021276  jz      short loc_180021282
0x180021278  mov     r8, [r8]
0x18002127b  cmp     r8, rax
0x18002127e  jnz     short loc_180021270
0x180021280  jmp     short loc_1800212AD
0x180021282  test    rdx, rdx
0x180021285  jz      short loc_1800212AD
0x180021287  mov     rax, [rdx+28h]
0x18002128b  lea     rcx, [rdi+8]
0x18002128f  mov     r8, [r8]
0x180021292  mov     [rax], r8
0x180021295  mov     [r8+8], rax
0x180021299  mov     rax, [rdx+18h]
0x18002129d  mov     r8, [rdx+10h]
0x1800212a1  mov     [rax], r8
0x1800212a4  mov     [r8+8], rax
0x1800212a8  call    ?Recycle@?$ObjectPool@UTABLE_ENTRY@?$TGenericMap@KK$0A@$04$0BD@@@$04@@QEAAXPEAUTABLE_ENTRY@?$TGenericMap@KK$0A@$04$0BD@@@@Z; ObjectPool<TGenericMap<ulong,ulong,0,5,19>::TABLE_ENTRY,5>::Recycle(TGenericMap<ulong,ulong,0,5,19>::TABLE_ENTRY *)
0x1800212ad  mov     rcx, r14; lpCriticalSection
0x1800212b0  call    cs:__imp_LeaveCriticalSection
0x1800212b6  mov     r8d, [rsi+34Ch]
0x1800212bd  mov     rcx, rdi
0x1800212c0  mov     edx, [rsi+348h]
0x1800212c6  call    ?Store@?$TGenericMap@KK$0A@$04$0BD@@@QEAAJKK@Z; TGenericMap<ulong,ulong,0,5,19>::Store(ulong,ulong)
0x1800212cb  jmp     short loc_1800212D5
0x1800212cd  mov     rcx, rdi
0x1800212d0  call    ?Clear@?$TGenericMap@KK$0A@$04$0BD@@@QEAAXXZ; TGenericMap<ulong,ulong,0,5,19>::Clear(void)
0x1800212d5  add     rsp, 20h
0x1800212d9  pop     r14
0x1800212db  pop     rdi
0x1800212dc  pop     rsi
0x1800212dd  pop     rbp
0x1800212de  pop     rbx
0x1800212df  retn
```
