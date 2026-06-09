# CPropertyCache::SetPropertyBuffer(ulong,ulong,uchar const *)

- ea: `0x14002a9f8`
- end: `0x14002aae5`
- name: `?SetPropertyBuffer@CPropertyCache@@QEAAHKKPEBE@Z`
- size: `237`
- prototype: `int(CPropertyCache *__hidden this, unsigned int, unsigned int, const unsigned __int8 *)`
- caller_count: `37`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140017590`
- `0x140020dc0`
- `0x140027530`
- `0x140027b68`
- `0x1400295b4`
- `0x14002c0e0`
- `0x140055f54`
- `0x140056d78`
- `0x140057148`
- `0x140057a5c`
- `0x1400581f8`
- `0x1400678c0`
- `0x140067c7c`
- `0x14006b664`
- `0x14006e5ec`
- `0x140072ae0`
- `0x140076d48`
- `0x140076eb8`
- `0x14007a820`
- `0x14007e5e0`
- `0x14007ee10`
- `0x1400836fc`
- `0x14008642c`
- `0x1400868e8`
- `0x140087eb8`
- `0x14008abd0`
- `0x14008ba40`
- `0x140090258`
- `0x1400b12a0`
- `0x1400b19b4`
- `0x1400b2ec0`
- `0x1400b511c`
- `0x1400bdb24`
- `0x1400be090`
- `0x1400be280`
- `0x1400c059c`
- `0x1400c5410`

## callees

- `0x14000c778`
- `0x140024230`
- `0x14002a9f8`

## pseudocode

```c
__int64 __fastcall CPropertyCache::SetPropertyBuffer(
        CPropertyCache *this,
        unsigned int a2,
        unsigned int a3,
        const unsigned __int8 *a4)
{
  unsigned int v6; // ebp
  unsigned int v7; // edi
  __int64 v8; // rbx
  __int64 v10; // [rsp+28h] [rbp-40h]
  int v11; // [rsp+28h] [rbp-40h]

  v6 = a2;
  if ( a2 >= *((_DWORD *)this + 2) )
  {
    v7 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v7;
    v11 = a2;
    LOBYTE(a2) = 2;
    v8 = 0;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      19,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v11);
  }
  else
  {
    v7 = 0;
    v8 = *((_QWORD *)this + 2) + 56LL * a2;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 5;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LODWORD(v10) = v7;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        22,
        (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
        v10);
    }
  }
  if ( !v7 )
  {
    v7 = _WFC_VARIABLE_BUFFER_PROPERTY::CopyBuffer((_WFC_VARIABLE_BUFFER_PROPERTY *)(v8 + 24), a3, a3, a4);
    if ( !v7 )
    {
      *(_DWORD *)v8 = v6;
      *(_DWORD *)(v8 + 4) = 4;
      *(_BYTE *)(v8 + 8) = 1;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x14002a9f8  push    rbx
0x14002a9fa  push    rbp
0x14002a9fb  push    rsi
0x14002a9fc  push    rdi
0x14002a9fd  push    r12
0x14002a9ff  push    r14
0x14002aa01  push    r15
0x14002aa03  sub     rsp, 30h
0x14002aa07  lea     r12, WPP_RECORDER_INITIALIZED
0x14002aa0e  mov     r14d, r8d
0x14002aa11  lea     r8, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14002aa18  mov     r15, r9
0x14002aa1b  mov     ebp, edx
0x14002aa1d  cmp     edx, [rcx+8]
0x14002aa20  jnb     short loc_14002AA30
0x14002aa22  xor     esi, esi
0x14002aa24  imul    rbx, rbp, 38h ; '8'
0x14002aa28  mov     edi, esi
0x14002aa2a  add     rbx, [rcx+10h]
0x14002aa2e  jmp     short loc_14002AA70
0x14002aa30  mov     edi, 0C000000Dh
0x14002aa35  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002aa3c  jz      loc_14002AAD3
0x14002aa42  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa49  xor     esi, esi
0x14002aa4b  mov     dword ptr [rsp+68h+var_40], ebp
0x14002aa4f  mov     dl, 2
0x14002aa51  mov     [rsp+68h+var_48], r8
0x14002aa56  mov     ebx, esi
0x14002aa58  mov     rcx, [rcx+40h]
0x14002aa5c  lea     r9d, [rsi+13h]
0x14002aa60  lea     r8d, [rsi+1]
0x14002aa64  call    WPP_RECORDER_SF_d
0x14002aa69  lea     r8, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14002aa70  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14002aa77  jz      short loc_14002AAA9
0x14002aa79  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa80  mov     dl, 5
0x14002aa82  cmp     [rcx+29h], dl
0x14002aa85  jnb     short loc_14002AA8D
0x14002aa87  cmp     [rcx+48h], si
0x14002aa8b  jz      short loc_14002AAA9
0x14002aa8d  mov     rcx, [rcx+40h]
0x14002aa91  mov     r9d, 16h
0x14002aa97  mov     dword ptr [rsp+68h+var_40], edi
0x14002aa9b  mov     [rsp+68h+var_48], r8
0x14002aaa0  lea     r8d, [r9-15h]
0x14002aaa4  call    WPP_RECORDER_SF_d
0x14002aaa9  test    edi, edi
0x14002aaab  jnz     short loc_14002AAD3
0x14002aaad  movzx   r8d, r14w; unsigned __int16
0x14002aab1  lea     rcx, [rbx+18h]; this
0x14002aab5  mov     r9, r15; unsigned __int8 *
0x14002aab8  mov     edx, r14d; unsigned int
0x14002aabb  call    ?CopyBuffer@_WFC_VARIABLE_BUFFER_PROPERTY@@QEAAHKGPEBE@Z; _WFC_VARIABLE_BUFFER_PROPERTY::CopyBuffer(ulong,ushort,uchar const *)
0x14002aac0  mov     edi, eax
0x14002aac2  test    eax, eax
0x14002aac4  jnz     short loc_14002AAD3
0x14002aac6  mov     [rbx], ebp
0x14002aac8  mov     dword ptr [rbx+4], 4
0x14002aacf  mov     byte ptr [rbx+8], 1
0x14002aad3  mov     eax, edi
0x14002aad5  add     rsp, 30h
0x14002aad9  pop     r15
0x14002aadb  pop     r14
0x14002aadd  pop     r12
0x14002aadf  pop     rdi
0x14002aae0  pop     rsi
0x14002aae1  pop     rbp
0x14002aae2  pop     rbx
0x14002aae3  retn
```
