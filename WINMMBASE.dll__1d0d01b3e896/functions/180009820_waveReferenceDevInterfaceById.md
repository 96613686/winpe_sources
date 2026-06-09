# waveReferenceDevInterfaceById

- ea: `0x180009820`
- end: `0x180009938`
- name: `waveReferenceDevInterfaceById`
- size: `280`
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

- `0x180004534`
- `0x180007560`
- `0x180007d70`
- `0x180009820`
- `0x18000dd28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009860`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009860`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000989b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000989b`

## pseudocode

```c
__int64 __fastcall waveReferenceDevInterfaceById(__int64 *a1, unsigned __int64 a2)
{
  unsigned __int64 v2; // rsi
  int v4; // ebp
  __int64 v5; // rbx
  __int64 v7; // rbx
  __int64 v8; // rdi

  v2 = a2;
  if ( a1 != &waveoutdrvZ || !ValidateHandle(a2, 1) )
  {
    v4 = 2;
    if ( a1 != (__int64 *)&waveindrvZ || !ValidateHandle(v2, 2) )
    {
      if ( (_DWORD)v2 == -1 )
        WaveMapperInit();
      EnterCriticalSection(&NumDevsCritSec);
      v5 = *a1;
      if ( (_DWORD)v2 == -1 )
      {
        while ( (__int64 *)v5 != a1 )
        {
          if ( (*(_BYTE *)(v5 + 112) & 2) != 0 )
            goto LABEL_12;
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
LABEL_12:
          _InterlockedIncrement((volatile signed __int32 *)(v5 + 92));
          v4 = 0;
          goto LABEL_13;
        }
      }
      v5 = 0;
LABEL_13:
      LeaveCriticalSection(&NumDevsCritSec);
      if ( v4 )
        return 0;
      v8 = *(_QWORD *)(v5 + 104);
      if ( *(_QWORD *)(v5 + 96) )
        wdmDevInterfaceInc();
      mregDecUsagePtr((struct _MMDRV *)v5);
      return v8;
    }
  }
  v7 = *(_QWORD *)(*(_QWORD *)v2 + 104LL);
  if ( *(_QWORD *)(*(_QWORD *)v2 + 96LL) )
    wdmDevInterfaceInc();
  return v7;
}

```

## disassembly

```asm
0x180009820  push    rbx
0x180009822  push    rbp
0x180009823  push    rsi
0x180009824  push    rdi
0x180009825  sub     rsp, 28h
0x180009829  lea     rax, waveoutdrvZ
0x180009830  mov     rsi, rdx
0x180009833  mov     rdi, rcx
0x180009836  cmp     rcx, rax
0x180009839  jz      short loc_1800098B0
0x18000983b  lea     rax, waveindrvZ
0x180009842  mov     ebp, 2
0x180009847  cmp     rdi, rax
0x18000984a  jz      loc_180009900
0x180009850  cmp     esi, 0FFFFFFFFh
0x180009853  jz      loc_180009927
0x180009859  lea     rcx, NumDevsCritSec; lpCriticalSection
0x180009860  call    cs:__imp_EnterCriticalSection
0x180009866  mov     rbx, [rdi]
0x180009869  cmp     esi, 0FFFFFFFFh
0x18000986c  jz      short loc_1800098DD
0x18000986e  cmp     rbx, rdi
0x180009871  jz      short loc_1800098E2
0x180009873  test    [rbx+70h], bpl
0x180009877  jnz     short loc_180009881
0x180009879  cmp     [rbx+58h], esi
0x18000987c  ja      short loc_180009889
0x18000987e  sub     esi, [rbx+58h]
0x180009881  mov     rbx, [rbx]
0x180009884  cmp     rbx, rdi
0x180009887  jnz     short loc_180009873
0x180009889  cmp     rbx, rdi
0x18000988c  jz      short loc_1800098E2
0x18000988e  lock inc dword ptr [rbx+5Ch]
0x180009892  xor     ebp, ebp
0x180009894  lea     rcx, NumDevsCritSec; lpCriticalSection
0x18000989b  call    cs:__imp_LeaveCriticalSection
0x1800098a1  test    ebp, ebp
0x1800098a3  jz      short loc_1800098E6
0x1800098a5  xor     eax, eax
0x1800098a7  add     rsp, 28h
0x1800098ab  pop     rdi
0x1800098ac  pop     rsi
0x1800098ad  pop     rbp
0x1800098ae  pop     rbx
0x1800098af  retn
0x1800098b0  mov     edx, 1
0x1800098b5  mov     rcx, rsi
0x1800098b8  call    ValidateHandle
0x1800098bd  test    eax, eax
0x1800098bf  jz      loc_18000983B
0x1800098c5  mov     rax, [rsi]
0x1800098c8  mov     rcx, [rax+60h]
0x1800098cc  mov     rbx, [rax+68h]
0x1800098d0  test    rcx, rcx
0x1800098d3  jnz     short loc_180009931
0x1800098d5  mov     rax, rbx
0x1800098d8  jmp     short loc_1800098A7
0x1800098da  mov     rbx, [rbx]
0x1800098dd  cmp     rbx, rdi
0x1800098e0  jnz     short loc_18000991B
0x1800098e2  xor     ebx, ebx
0x1800098e4  jmp     short loc_180009894
0x1800098e6  mov     rcx, [rbx+60h]
0x1800098ea  mov     rdi, [rbx+68h]
0x1800098ee  test    rcx, rcx
0x1800098f1  jnz     short loc_180009914
0x1800098f3  mov     rcx, rbx; struct _MMDRV *
0x1800098f6  call    mregDecUsagePtr
0x1800098fb  mov     rax, rdi
0x1800098fe  jmp     short loc_1800098A7
0x180009900  mov     edx, ebp
0x180009902  mov     rcx, rsi
0x180009905  call    ValidateHandle
0x18000990a  test    eax, eax
0x18000990c  jz      loc_180009850
0x180009912  jmp     short loc_1800098C5
0x180009914  call    wdmDevInterfaceInc
0x180009919  jmp     short loc_1800098F3
0x18000991b  test    [rbx+70h], bpl
0x18000991f  jnz     loc_18000988E
0x180009925  jmp     short loc_1800098DA
0x180009927  call    WaveMapperInit
0x18000992c  jmp     loc_180009859
0x180009931  call    wdmDevInterfaceInc
0x180009936  jmp     short loc_1800098D5
```
