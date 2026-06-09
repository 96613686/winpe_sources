# waveReferenceDriverById

- ea: `0x180004480`
- end: `0x18000452e`
- name: `waveReferenceDriverById`
- size: `174`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180001378`
- `0x1800048e0`
- `0x180005030`
- `0x18000b364`
- `0x18000b8f4`
- `0x18000fd94`

## callees

- `0x180004480`
- `0x180004534`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800044a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000450a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800044a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000450a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800044ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800044ec`

## pseudocode

```c
__int64 __fastcall waveReferenceDriverById(_QWORD *a1, unsigned int a2, _QWORD *a3, unsigned int *a4)
{
  unsigned int i; // edi
  _QWORD *v8; // rax
  unsigned int v9; // ecx
  unsigned int v10; // ebx

  i = a2;
  if ( a2 == -1 )
  {
    WaveMapperInit();
    EnterCriticalSection(&NumDevsCritSec);
    v8 = (_QWORD *)*a1;
    for ( i = 0; v8 != a1; v8 = (_QWORD *)*v8 )
    {
      if ( (v8[14] & 2) != 0 )
        goto LABEL_6;
    }
    goto LABEL_11;
  }
  EnterCriticalSection(&NumDevsCritSec);
  v8 = (_QWORD *)*a1;
  if ( (_QWORD *)*a1 == a1 )
  {
LABEL_11:
    v10 = 2;
    goto LABEL_12;
  }
  while ( (v8[14] & 2) != 0 )
  {
LABEL_10:
    v8 = (_QWORD *)*v8;
    if ( v8 == a1 )
      goto LABEL_11;
  }
  v9 = *((_DWORD *)v8 + 22);
  if ( v9 <= i )
  {
    i -= v9;
    goto LABEL_10;
  }
  if ( v8 == a1 )
    goto LABEL_11;
LABEL_6:
  if ( a3 )
  {
    _InterlockedIncrement((volatile signed __int32 *)v8 + 23);
    *a3 = v8;
    if ( a4 )
      *a4 = i;
  }
  v10 = 0;
LABEL_12:
  LeaveCriticalSection(&NumDevsCritSec);
  return v10;
}

```

## disassembly

```asm
0x180004480  push    rbx
0x180004482  push    rsi
0x180004483  push    rdi
0x180004484  push    r14
0x180004486  sub     rsp, 28h
0x18000448a  mov     rsi, r9
0x18000448d  mov     r14, r8
0x180004490  mov     edi, edx
0x180004492  mov     rbx, rcx
0x180004495  cmp     edx, 0FFFFFFFFh
0x180004498  jz      short loc_1800044FE
0x18000449a  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800044a1  call    cs:__imp_EnterCriticalSection
0x1800044a7  mov     rax, [rbx]
0x1800044aa  cmp     rax, rbx
0x1800044ad  jz      short loc_1800044E0
0x1800044af  test    byte ptr [rax+70h], 2
0x1800044b3  jnz     short loc_1800044D8
0x1800044b5  mov     ecx, [rax+58h]
0x1800044b8  cmp     ecx, edi
0x1800044ba  jbe     short loc_18000452A
0x1800044bc  cmp     rax, rbx
0x1800044bf  jz      short loc_1800044E0
0x1800044c1  test    r14, r14
0x1800044c4  jz      short loc_1800044D4
0x1800044c6  lock inc dword ptr [rax+5Ch]
0x1800044ca  mov     [r14], rax
0x1800044cd  test    rsi, rsi
0x1800044d0  jz      short loc_1800044D4
0x1800044d2  mov     [rsi], edi
0x1800044d4  xor     ebx, ebx
0x1800044d6  jmp     short loc_1800044E5
0x1800044d8  mov     rax, [rax]
0x1800044db  cmp     rax, rbx
0x1800044de  jnz     short loc_1800044AF
0x1800044e0  mov     ebx, 2
0x1800044e5  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800044ec  call    cs:__imp_LeaveCriticalSection
0x1800044f2  mov     eax, ebx
0x1800044f4  add     rsp, 28h
0x1800044f8  pop     r14
0x1800044fa  pop     rdi
0x1800044fb  pop     rsi
0x1800044fc  pop     rbx
0x1800044fd  retn
0x1800044fe  call    WaveMapperInit
0x180004503  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000450a  call    cs:__imp_EnterCriticalSection
0x180004510  mov     rax, [rbx]
0x180004513  xor     edi, edi
0x180004515  cmp     rax, rbx
0x180004518  jz      short loc_1800044E0
0x18000451a  test    byte ptr [rax+70h], 2
0x18000451e  jnz     short loc_1800044C1
0x180004520  mov     rax, [rax]
0x180004523  cmp     rax, rbx
0x180004526  jz      short loc_1800044E0
0x180004528  jmp     short loc_18000451A
0x18000452a  sub     edi, ecx
0x18000452c  jmp     short loc_1800044D8
```
