# IMixerMessageId(uint,uint,unsigned __int64,unsigned __int64)

- ea: `0x18000ffc0`
- end: `0x18001011e`
- name: `?IMixerMessageId@@YAKII_K0@Z`
- size: `350`
- prototype: `unsigned int __fastcall(UINT uMxId, unsigned int, unsigned __int64, unsigned __int64)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x18000af80`
- `0x18000b090`
- `0x18000b800`
- `0x180019c9c`
- `0x18001a7a0`
- `0x18001ac10`
- `0x18001ac80`

## callees

- `0x180007d70`
- `0x180007dd0`
- `0x18000a960`
- `0x18000ffc0`
- `0x18001a3c0`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ffef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800100d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ffef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800100d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001003f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800100f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001003f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800100f8`

## pseudocode

```c
__int64 __fastcall IMixerMessageId(UINT uMxId, unsigned int a2, unsigned __int16 *a3, unsigned __int64 a4)
{
  UINT v5; // esi
  struct _MMDRV *v9; // rbx
  unsigned int v10; // ebp
  MMRESULT v11; // edi
  HMIXER v13; // rsi
  __int64 v14; // rdi
  MMRESULT v15; // eax
  struct _RTL_CRITICAL_SECTION *v16; // rcx
  HMIXER phmx; // [rsp+40h] [rbp-58h] BYREF
  __int64 v18; // [rsp+A0h] [rbp+8h] BYREF

  phmx = 0;
  v5 = uMxId;
  EnterCriticalSection(&NumDevsCritSec);
  v9 = mixerdrvZ;
  v10 = v5;
  v11 = 2;
  if ( mixerdrvZ == (struct _MMDRV *)&mixerdrvZ )
    goto LABEL_8;
  do
  {
    if ( (*((_BYTE *)v9 + 112) & 2) == 0 )
    {
      if ( *((_DWORD *)v9 + 22) > v5 )
        break;
      v5 -= *((_DWORD *)v9 + 22);
    }
    v9 = *(struct _MMDRV **)v9;
    v10 = v5;
  }
  while ( v9 != (struct _MMDRV *)&mixerdrvZ );
  if ( v9 == (struct _MMDRV *)&mixerdrvZ )
  {
LABEL_8:
    v9 = 0;
    v10 = 0;
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)v9 + 23);
    v11 = 0;
  }
  LeaveCriticalSection(&NumDevsCritSec);
  LODWORD(v18) = v11;
  if ( !v11 )
  {
    if ( (unsigned int)mregHandleInternalMessages(v9, 8, v10, a2, a3, a4, (int *)&v18) )
    {
      mregDecUsagePtr(v9);
      return (unsigned int)v18;
    }
    mregDecUsagePtr(v9);
    v11 = mixerOpen(&phmx, uMxId, 0, 0, 0);
    if ( !v11 )
    {
      v13 = phmx;
      v14 = *((_QWORD *)phmx + 2);
      if ( *(_QWORD *)(v14 + 80) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 120));
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, unsigned __int16 *, unsigned __int64))(v14 + 80))(
                v10,
                a2,
                *((_QWORD *)v13 + 4),
                a3,
                a4);
        v16 = (struct _RTL_CRITICAL_SECTION *)(v14 + 120);
        v11 = v15;
        LeaveCriticalSection(v16);
        v13 = phmx;
      }
      else
      {
        v11 = 6;
      }
      mixerClose(v13);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x18000ffc0  push    rbx
0x18000ffc2  push    rbp
0x18000ffc3  push    rsi
0x18000ffc4  push    rdi
0x18000ffc5  push    r12
0x18000ffc7  push    r13
0x18000ffc9  push    r14
0x18000ffcb  push    r15
0x18000ffcd  sub     rsp, 58h
0x18000ffd1  mov     r14d, ecx
0x18000ffd4  mov     [rsp+98h+phmx], 0
0x18000ffdd  mov     esi, ecx
0x18000ffdf  mov     r15, r9
0x18000ffe2  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000ffe9  mov     r12, r8
0x18000ffec  mov     r13d, edx
0x18000ffef  call    cs:__imp_EnterCriticalSection
0x18000fff5  mov     rbx, cs:mixerdrvZ
0x18000fffc  lea     rax, mixerdrvZ
0x180010003  mov     ebp, esi
0x180010005  mov     edi, 2
0x18001000a  cmp     rbx, rax
0x18001000d  jz      short loc_180010034
0x18001000f  test    [rbx+70h], dil
0x180010013  jnz     short loc_18001001D
0x180010015  cmp     [rbx+58h], esi
0x180010018  ja      short loc_180010027
0x18001001a  sub     esi, [rbx+58h]
0x18001001d  mov     rbx, [rbx]
0x180010020  mov     ebp, esi
0x180010022  cmp     rbx, rax
0x180010025  jnz     short loc_18001000F
0x180010027  cmp     rbx, rax
0x18001002a  jz      short loc_180010034
0x18001002c  lock inc dword ptr [rbx+5Ch]
0x180010030  xor     edi, edi
0x180010032  jmp     short loc_180010038
0x180010034  xor     ebx, ebx
0x180010036  xor     ebp, ebp
0x180010038  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18001003f  call    cs:__imp_LeaveCriticalSection
0x180010045  mov     dword ptr [rsp+98h+arg_0], edi
0x18001004c  test    edi, edi
0x18001004e  jnz     loc_18001010B
0x180010054  lea     rax, [rsp+98h+arg_0]
0x18001005c  mov     r9d, r13d
0x18001005f  mov     [rsp+98h+var_68], rax; __int64
0x180010064  lea     edx, [rdi+8]
0x180010067  mov     [rsp+98h+var_70], r15; unsigned __int64
0x18001006c  mov     r8d, ebp
0x18001006f  mov     rcx, rbx; struct _MMDRV *
0x180010072  mov     qword ptr [rsp+98h+fdwOpen], r12; unsigned __int16 *
0x180010077  call    mregHandleInternalMessages
0x18001007c  mov     rcx, rbx; struct _MMDRV *
0x18001007f  test    eax, eax
0x180010081  jz      short loc_180010091
0x180010083  call    mregDecUsagePtr
0x180010088  mov     eax, dword ptr [rsp+98h+arg_0]
0x18001008f  jmp     short loc_18001010D
0x180010091  call    mregDecUsagePtr
0x180010096  xor     r9d, r9d; dwInstance
0x180010099  mov     [rsp+98h+fdwOpen], 0; fdwOpen
0x1800100a1  xor     r8d, r8d; dwCallback
0x1800100a4  lea     rcx, [rsp+98h+phmx]; phmx
0x1800100a9  mov     edx, r14d; uMxId
0x1800100ac  call    mixerOpen
0x1800100b1  mov     edi, eax
0x1800100b3  test    eax, eax
0x1800100b5  jnz     short loc_18001010B
0x1800100b7  mov     rsi, [rsp+98h+phmx]
0x1800100bc  mov     rdi, [rsi+10h]
0x1800100c0  cmp     qword ptr [rdi+50h], 0
0x1800100c5  jnz     short loc_1800100CC
0x1800100c7  lea     edi, [rax+6]
0x1800100ca  jmp     short loc_180010103
0x1800100cc  lea     rbx, [rdi+78h]
0x1800100d0  mov     rcx, rbx; lpCriticalSection
0x1800100d3  call    cs:__imp_EnterCriticalSection
0x1800100d9  mov     r8, [rsi+20h]
0x1800100dd  mov     r9, r12
0x1800100e0  mov     rax, [rdi+50h]
0x1800100e4  mov     edx, r13d
0x1800100e7  mov     ecx, ebp
0x1800100e9  mov     qword ptr [rsp+98h+fdwOpen], r15
0x1800100ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100f3  mov     rcx, rbx; lpCriticalSection
0x1800100f6  mov     edi, eax
0x1800100f8  call    cs:__imp_LeaveCriticalSection
0x1800100fe  mov     rsi, [rsp+98h+phmx]
0x180010103  mov     rcx, rsi; hmx
0x180010106  call    mixerClose
0x18001010b  mov     eax, edi
0x18001010d  add     rsp, 58h
0x180010111  pop     r15
0x180010113  pop     r14
0x180010115  pop     r13
0x180010117  pop     r12
0x180010119  pop     rdi
0x18001011a  pop     rsi
0x18001011b  pop     rbp
0x18001011c  pop     rbx
0x18001011d  retn
```
