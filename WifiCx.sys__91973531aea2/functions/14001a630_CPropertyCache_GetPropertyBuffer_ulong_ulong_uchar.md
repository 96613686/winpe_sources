# CPropertyCache::GetPropertyBuffer(ulong,ulong *,uchar * *)

- ea: `0x14001a630`
- end: `0x14001a74a`
- name: `?GetPropertyBuffer@CPropertyCache@@QEAAHKPEAKPEAPEAE@Z`
- size: `282`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int, unsigned int *, unsigned __int8 **)`
- caller_count: `48`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140011f9c`
- `0x140017a90`
- `0x140020dc0`
- `0x140027b68`
- `0x140028b40`
- `0x1400295b4`
- `0x14002c0e0`
- `0x14002e080`
- `0x140055850`
- `0x140055f54`
- `0x1400565c4`
- `0x140057a5c`
- `0x1400581f8`
- `0x140067034`
- `0x1400670f8`
- `0x1400671c8`
- `0x1400672f0`
- `0x1400673d4`
- `0x140068a94`
- `0x14007b9a0`
- `0x14007cd10`
- `0x14007cf70`
- `0x140080488`
- `0x1400836fc`
- `0x140085c34`
- `0x1400860d4`
- `0x14008642c`
- `0x140088270`
- `0x1400a19c0`
- `0x1400a1f9c`
- `0x1400a2b64`
- `0x1400a3584`
- `0x1400a621c`
- `0x1400a6c04`
- `0x1400a73d4`
- `0x1400b0128`
- `0x1400b0448`
- `0x1400b1110`
- `0x1400b19b4`
- `0x1400b37f8`
- `0x1400be910`
- `0x1400c4c60`
- `0x1400c5410`
- `0x1400c6450`
- `0x1400c7268`
- `0x1400cded4`
- `0x1400d1010`
- `0x1400d3430`

## callees

- `0x14000c778`
- `0x14001a630`

## pseudocode

```c
__int64 __fastcall CPropertyCache::GetPropertyBuffer(
        CPropertyCache *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  __int64 v4; // rdi
  __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v10; // [rsp+28h] [rbp-40h]
  int v11; // [rsp+28h] [rbp-40h]
  int v12; // [rsp+28h] [rbp-40h]

  v4 = 0;
  if ( a2 >= *((_DWORD *)this + 2) )
  {
    v8 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v8;
    v12 = a2;
    LOBYTE(a2) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      19,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v12);
  }
  else
  {
    v7 = 56LL * a2 + *((_QWORD *)this + 2);
    if ( *(_BYTE *)(v7 + 8) )
    {
      v4 = v7;
    }
    else
    {
      if ( !*(_QWORD *)(v7 + 48) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v11 = a2;
          LOBYTE(a2) = 4;
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            1,
            20,
            (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
            v11);
        }
        v8 = -1073741436;
        goto LABEL_12;
      }
      v4 = *(_QWORD *)(v7 + 48);
    }
    v8 = 0;
  }
LABEL_12:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v10) = v8;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      22,
      (__int64)WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids,
      v10);
  }
  if ( !v8 )
  {
    *a3 = *(_DWORD *)(v4 + 32);
    *a4 = *(unsigned __int8 **)(v4 + 24);
  }
  return v8;
}

```

## disassembly

```asm
0x14001a630  push    rbx
0x14001a632  push    rbp
0x14001a633  push    rsi
0x14001a634  push    rdi
0x14001a635  push    r14
0x14001a637  push    r15
0x14001a639  sub     rsp, 38h
0x14001a63d  xor     edi, edi
0x14001a63f  lea     rbp, WPP_RECORDER_INITIALIZED
0x14001a646  lea     r15, WPP_3ddeec0b7fee33ed2b3cc846f6231af9_Traceguids
0x14001a64d  mov     rsi, r9
0x14001a650  mov     r14, r8
0x14001a653  cmp     edx, [rcx+8]
0x14001a656  jnb     short loc_14001A6B7
0x14001a658  mov     rcx, [rcx+10h]
0x14001a65c  mov     eax, edx
0x14001a65e  imul    r10, rax, 38h ; '8'
0x14001a662  add     rcx, r10
0x14001a665  cmp     [rcx+8], dil
0x14001a669  jnz     short loc_14001A6B0
0x14001a66b  mov     rax, [rcx+30h]
0x14001a66f  test    rax, rax
0x14001a672  jnz     short loc_14001A6AB
0x14001a674  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001a67b  jz      short loc_14001A6A4
0x14001a67d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a684  mov     r9d, 14h
0x14001a68a  mov     dword ptr [rsp+68h+var_40], edx
0x14001a68e  mov     r8d, 1
0x14001a694  mov     dl, 4
0x14001a696  mov     [rsp+68h+var_48], r15
0x14001a69b  mov     rcx, [rcx+40h]
0x14001a69f  call    WPP_RECORDER_SF_d
0x14001a6a4  mov     ebx, 0C0000184h
0x14001a6a9  jmp     short loc_14001A6EC
0x14001a6ab  mov     rdi, rax
0x14001a6ae  jmp     short loc_14001A6B3
0x14001a6b0  mov     rdi, rcx
0x14001a6b3  xor     ebx, ebx
0x14001a6b5  jmp     short loc_14001A6EC
0x14001a6b7  mov     ebx, 0C000000Dh
0x14001a6bc  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001a6c3  jz      short loc_14001A73A
0x14001a6c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6cc  mov     r9d, 13h
0x14001a6d2  mov     dword ptr [rsp+68h+var_40], edx
0x14001a6d6  mov     r8d, 1
0x14001a6dc  mov     dl, 2
0x14001a6de  mov     [rsp+68h+var_48], r15
0x14001a6e3  mov     rcx, [rcx+40h]
0x14001a6e7  call    WPP_RECORDER_SF_d
0x14001a6ec  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14001a6f3  jz      short loc_14001A729
0x14001a6f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6fc  cmp     byte ptr [rcx+29h], 5
0x14001a700  jnb     short loc_14001A709
0x14001a702  cmp     word ptr [rcx+48h], 0
0x14001a707  jz      short loc_14001A729
0x14001a709  mov     rcx, [rcx+40h]
0x14001a70d  mov     r9d, 16h
0x14001a713  mov     dword ptr [rsp+68h+var_40], ebx
0x14001a717  mov     r8d, 1
0x14001a71d  mov     dl, 5
0x14001a71f  mov     [rsp+68h+var_48], r15
0x14001a724  call    WPP_RECORDER_SF_d
0x14001a729  test    ebx, ebx
0x14001a72b  jnz     short loc_14001A73A
0x14001a72d  mov     eax, [rdi+20h]
0x14001a730  mov     [r14], eax
0x14001a733  mov     rax, [rdi+18h]
0x14001a737  mov     [rsi], rax
0x14001a73a  mov     eax, ebx
0x14001a73c  add     rsp, 38h
0x14001a740  pop     r15
0x14001a742  pop     r14
0x14001a744  pop     rdi
0x14001a745  pop     rsi
0x14001a746  pop     rbp
0x14001a747  pop     rbx
0x14001a748  retn
```
