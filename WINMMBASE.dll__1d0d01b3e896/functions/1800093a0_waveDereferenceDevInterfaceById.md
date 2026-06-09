# waveDereferenceDevInterfaceById

- ea: `0x1800093a0`
- end: `0x18000949e`
- name: `waveDereferenceDevInterfaceById`
- size: `254`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x1800094f4`
- `0x180009760`
- `0x18000a790`
- `0x18000ec90`
- `0x18000ed70`
- `0x18000eff0`
- `0x18000f498`
- `0x18001da90`

## callees

- `0x180002558`
- `0x180004534`
- `0x180007560`
- `0x180007d70`
- `0x1800093a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800093f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800093f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009430`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009430`

## pseudocode

```c
void __fastcall waveDereferenceDevInterfaceById(__int64 *a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rsi
  int v4; // ebp
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = a2;
  if ( a1 == &waveoutdrvZ && ValidateHandle(a2, 1) || (v4 = 2, a1 == (__int64 *)&waveindrvZ) && ValidateHandle(v2, 2) )
  {
    v7 = *(_QWORD *)(*(_QWORD *)v2 + 96LL);
    if ( v7 )
      wdmDevInterfaceDec(v7);
    return;
  }
  if ( (_DWORD)v2 == -1 )
    WaveMapperInit();
  EnterCriticalSection(&NumDevsCritSec);
  v5 = *a1;
  if ( (_DWORD)v2 == -1 )
  {
    while ( (__int64 *)v5 != a1 )
    {
      if ( (*(_BYTE *)(v5 + 112) & 2) != 0 )
        goto LABEL_13;
      v5 = *(_QWORD *)v5;
    }
  }
  else if ( (__int64 *)v5 != a1 )
  {
    do
    {
      if ( (*(_BYTE *)(v5 + 112) & 2) == 0 )
      {
        if ( *(_DWORD *)(v5 + 88) > (unsigned int)v2 )
          break;
        LODWORD(v2) = v2 - *(_DWORD *)(v5 + 88);
      }
      v5 = *(_QWORD *)v5;
    }
    while ( (__int64 *)v5 != a1 );
    if ( (__int64 *)v5 != a1 )
    {
LABEL_13:
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 92));
      v4 = 0;
      goto LABEL_14;
    }
  }
  v5 = 0;
LABEL_14:
  LeaveCriticalSection(&NumDevsCritSec);
  if ( !v4 )
  {
    v6 = *(_QWORD *)(v5 + 96);
    if ( v6 )
      wdmDevInterfaceDec(v6);
    mregDecUsagePtr((struct _MMDRV *)v5);
  }
}

```

## disassembly

```asm
0x1800093a0  push    rbx
0x1800093a2  push    rbp
0x1800093a3  push    rsi
0x1800093a4  push    rdi
0x1800093a5  sub     rsp, 28h
0x1800093a9  lea     rax, waveoutdrvZ
0x1800093b0  mov     rsi, rdx
0x1800093b3  mov     rdi, rcx
0x1800093b6  cmp     rcx, rax
0x1800093b9  jnz     short loc_1800093D0
0x1800093bb  mov     edx, 1
0x1800093c0  mov     rcx, rsi
0x1800093c3  call    ValidateHandle
0x1800093c8  test    eax, eax
0x1800093ca  jnz     loc_18000948B
0x1800093d0  lea     rax, waveindrvZ
0x1800093d7  mov     ebp, 2
0x1800093dc  cmp     rdi, rax
0x1800093df  jz      loc_180009479
0x1800093e5  cmp     esi, 0FFFFFFFFh
0x1800093e8  jz      loc_18000946F
0x1800093ee  lea     rcx, NumDevsCritSec; lpCriticalSection
0x1800093f5  call    cs:__imp_EnterCriticalSection
0x1800093fb  mov     rbx, [rdi]
0x1800093fe  cmp     esi, 0FFFFFFFFh
0x180009401  jz      short loc_180009457
0x180009403  cmp     rbx, rdi
0x180009406  jz      short loc_18000945C
0x180009408  test    [rbx+70h], bpl
0x18000940c  jnz     short loc_180009416
0x18000940e  cmp     [rbx+58h], esi
0x180009411  ja      short loc_18000941E
0x180009413  sub     esi, [rbx+58h]
0x180009416  mov     rbx, [rbx]
0x180009419  cmp     rbx, rdi
0x18000941c  jnz     short loc_180009408
0x18000941e  cmp     rbx, rdi
0x180009421  jz      short loc_18000945C
0x180009423  lock inc dword ptr [rbx+5Ch]
0x180009427  xor     ebp, ebp
0x180009429  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180009430  call    cs:__imp_LeaveCriticalSection
0x180009436  test    ebp, ebp
0x180009438  jnz     short loc_18000944B
0x18000943a  mov     rcx, [rbx+60h]
0x18000943e  test    rcx, rcx
0x180009441  jnz     short loc_180009460
0x180009443  mov     rcx, rbx; struct _MMDRV *
0x180009446  call    mregDecUsagePtr
0x18000944b  add     rsp, 28h
0x18000944f  pop     rdi
0x180009450  pop     rsi
0x180009451  pop     rbp
0x180009452  pop     rbx
0x180009453  retn
0x180009454  mov     rbx, [rbx]
0x180009457  cmp     rbx, rdi
0x18000945a  jnz     short loc_180009467
0x18000945c  xor     ebx, ebx
0x18000945e  jmp     short loc_180009429
0x180009460  call    wdmDevInterfaceDec
0x180009465  jmp     short loc_180009443
0x180009467  test    [rbx+70h], bpl
0x18000946b  jnz     short loc_180009423
0x18000946d  jmp     short loc_180009454
0x18000946f  call    WaveMapperInit
0x180009474  jmp     loc_1800093EE
0x180009479  mov     edx, ebp
0x18000947b  mov     rcx, rsi
0x18000947e  call    ValidateHandle
0x180009483  test    eax, eax
0x180009485  jz      loc_1800093E5
0x18000948b  mov     rax, [rsi]
0x18000948e  mov     rcx, [rax+60h]
0x180009492  test    rcx, rcx
0x180009495  jz      short loc_18000944B
0x180009497  call    wdmDevInterfaceDec
0x18000949c  jmp     short loc_18000944B
```
