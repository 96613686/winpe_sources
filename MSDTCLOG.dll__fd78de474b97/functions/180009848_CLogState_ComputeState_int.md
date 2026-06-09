# CLogState::_ComputeState(int)

- ea: `0x180009848`
- end: `0x18000992c`
- name: `?_ComputeState@CLogState@@AEAAXH@Z`
- size: `228`
- prototype: `void __fastcall(CLogState *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006328`
- `0x180009050`

## callees

- `0x180009848`
- `0x18001266c`

## pseudocode

```c
void __fastcall CLogState::_ComputeState(CLogState *this, int a2)
{
  unsigned int v2; // r8d
  unsigned int v4; // r11d
  BOOL v5; // eax
  int v6; // r10d
  int v7; // edx
  unsigned int v8; // esi
  int v9; // edi
  int v10; // ecx
  unsigned int v11; // eax
  unsigned int v12; // eax
  int pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  pExceptionObject = a2;
  v2 = *((_DWORD *)this + 6);
  v4 = *((_DWORD *)this + 20);
  v5 = v2 >= *((_DWORD *)this + 8);
  *((_DWORD *)this + 2) = v2;
  *((_DWORD *)this + 3) = v5;
  v6 = -v4;
  v7 = v2 & ~(v4 - 1);
  *((_DWORD *)this + 27) = v7;
  *((_DWORD *)this + 28) = v2 - v7 - 32;
  v8 = v7 + v4;
  v9 = v7 - v2 + 0x2000;
  *((_DWORD *)this + 29) = v9;
  *((_DWORD *)this + 30) = v7 + v4;
  if ( *((_DWORD *)this + 8) > v2 )
  {
    v10 = ((*((_DWORD *)this + 8) & ~(v4 - 1)) - 1) / v4 - (v8 & v6) / v4;
    v11 = 0;
  }
  else
  {
    v10 = *((_DWORD *)this + 1) - v8 / v4;
    v11 = (*((_DWORD *)this + 8) & (unsigned int)v6) / v4 - 4;
  }
  *((_DWORD *)this + 31) = v10;
  *((_DWORD *)this + 32) = v11;
  v12 = v9 + 8160 * (v10 + v11);
  *((_DWORD *)this + 4) = v12;
  if ( v12 > *((_DWORD *)this + 19) )
  {
    pExceptionObject = -2147418113;
    throw (long *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180009848  mov     [rsp+arg_0], rsi
0x18000984d  mov     [rsp+pExceptionObject], edx
0x180009851  push    rdi
0x180009852  sub     rsp, 20h
0x180009856  mov     r8d, [rcx+18h]
0x18000985a  xor     eax, eax
0x18000985c  cmp     r8d, [rcx+20h]
0x180009860  mov     r9, rcx
0x180009863  mov     r11d, [rcx+50h]
0x180009867  mov     r10d, r11d
0x18000986a  setnb   al
0x18000986d  mov     [rcx+8], r8d
0x180009871  mov     [rcx+0Ch], eax
0x180009874  neg     r10d
0x180009877  mov     eax, r8d
0x18000987a  lea     ecx, [r11-1]
0x18000987e  not     ecx
0x180009880  mov     edx, ecx
0x180009882  and     edx, r8d
0x180009885  sub     eax, edx
0x180009887  mov     [r9+6Ch], edx
0x18000988b  mov     edi, edx
0x18000988d  sub     eax, 20h ; ' '
0x180009890  sub     edi, r8d
0x180009893  mov     [r9+70h], eax
0x180009897  lea     esi, [rdx+r11]
0x18000989b  add     edi, 2000h
0x1800098a1  xor     edx, edx
0x1800098a3  mov     [r9+74h], edi
0x1800098a7  mov     [r9+78h], esi
0x1800098ab  cmp     [r9+20h], r8d
0x1800098af  ja      short loc_1800098CD
0x1800098b1  and     r10d, [r9+20h]
0x1800098b5  mov     eax, esi
0x1800098b7  mov     ecx, [r9+4]
0x1800098bb  div     r11d
0x1800098be  xor     edx, edx
0x1800098c0  sub     ecx, eax
0x1800098c2  mov     eax, r10d
0x1800098c5  div     r11d
0x1800098c8  sub     eax, 4
0x1800098cb  jmp     short loc_1800098E8
0x1800098cd  and     ecx, [r9+20h]
0x1800098d1  and     r10d, esi
0x1800098d4  lea     eax, [rcx-1]
0x1800098d7  div     r11d
0x1800098da  xor     edx, edx
0x1800098dc  mov     ecx, eax
0x1800098de  mov     eax, r10d
0x1800098e1  div     r11d
0x1800098e4  sub     ecx, eax
0x1800098e6  xor     eax, eax
0x1800098e8  mov     [r9+7Ch], ecx
0x1800098ec  mov     [r9+80h], eax
0x1800098f3  add     eax, ecx
0x1800098f5  imul    eax, 1FE0h
0x1800098fb  add     eax, edi
0x1800098fd  mov     [r9+10h], eax
0x180009901  cmp     eax, [r9+4Ch]
0x180009905  ja      short loc_180009912
0x180009907  mov     rsi, [rsp+28h+arg_0]
0x18000990c  add     rsp, 20h
0x180009910  pop     rdi
0x180009911  retn
0x180009912  lea     rdx, _TI1J; pThrowInfo
0x180009919  mov     [rsp+28h+pExceptionObject], 8000FFFFh
0x180009921  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180009926  call    _CxxThrowException_0
```
