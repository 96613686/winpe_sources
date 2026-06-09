# CTieredVolume::DereferenceVolume(void)

- ea: `0x14000ccc0`
- end: `0x14000ce40`
- name: `?DereferenceVolume@CTieredVolume@@QEAAXXZ`
- size: `384`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `23`
- callee_count: `3`
- tags: ``

## callers

- `0x14000d5f0`
- `0x14000f2e4`
- `0x140010d1c`
- `0x1400211a4`
- `0x140036390`
- `0x140038490`
- `0x14003a3d0`
- `0x14003ad70`
- `0x14003c7e8`
- `0x14003ca54`
- `0x14003cde0`
- `0x14003cfb4`
- `0x14003d2ec`
- `0x14003d800`
- `0x14003da18`
- `0x14003db78`
- `0x14003ddd4`
- `0x14003e49c`
- `0x14003e794`
- `0x14003e8ec`
- `0x14003e9d0`
- `0x14003eba8`
- `0x14003f4d8`

## callees

- `0x14000ccc0`
- `0x140017930`
- `0x140017e78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000cd4c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000cd62`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000cd4c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000cd62`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ce30`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000ce30`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000cdeb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000cdeb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ccd4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000ccd4`

## pseudocode

```c
void __fastcall CTieredVolume::DereferenceVolume(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  int Ptr; // eax
  int v4; // esi
  _QWORD *v5; // rcx

  v1 = this + 3;
  AcquireSRWLockExclusive(this + 3);
  Ptr = (int)this[89].Ptr;
  v4 = Ptr - 1;
  if ( Ptr )
  {
    LODWORD(this[89].Ptr) = v4;
LABEL_7:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 132, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, &this[18]);
    goto LABEL_7;
  }
LABEL_8:
  if ( !BYTE5(this[20].Ptr) && !BYTE6(this[20].Ptr) )
  {
    if ( WaitForSingleObject(this[96].Ptr, 0) == 258 && WaitForSingleObject(this[95].Ptr, 0) == 258 )
      goto LABEL_27;
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 5u )
  {
    WPP_SF_Z(v5[2], 252, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, &this[84]);
    v5 = WPP_GLOBAL_Control;
  }
  if ( LODWORD(this[89].Ptr) )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
      WPP_SF_dZ(v5[2], 134, (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, v4, (__int64)&this[18]);
  }
  else
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 4u )
      WPP_SF_Z(v5[2], 133, &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids, &this[18]);
    SetEvent(this[97].Ptr);
  }
LABEL_27:
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x14000ccc0  push    rbx
0x14000ccc2  push    rsi
0x14000ccc3  push    rdi
0x14000ccc4  push    r14
0x14000ccc6  sub     rsp, 38h
0x14000ccca  lea     rdi, [rcx+18h]
0x14000ccce  mov     rbx, rcx
0x14000ccd1  mov     rcx, rdi; SRWLock
0x14000ccd4  call    cs:__imp_AcquireSRWLockExclusive
0x14000ccda  mov     eax, [rbx+2C8h]
0x14000cce0  lea     r14, WPP_GLOBAL_Control
0x14000cce7  lea     esi, [rax-1]
0x14000ccea  test    eax, eax
0x14000ccec  jz      short loc_14000CCF6
0x14000ccee  mov     [rbx+2C8h], esi
0x14000ccf4  jmp     short loc_14000CD2A
0x14000ccf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ccfd  cmp     rcx, r14
0x14000cd00  jz      short loc_14000CD31
0x14000cd02  test    byte ptr [rcx+1Ch], 1
0x14000cd06  jz      short loc_14000CD31
0x14000cd08  cmp     byte ptr [rcx+19h], 2
0x14000cd0c  jb      short loc_14000CD31
0x14000cd0e  mov     rcx, [rcx+10h]
0x14000cd12  lea     r9, [rbx+90h]
0x14000cd19  mov     edx, 84h
0x14000cd1e  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000cd25  call    WPP_SF_Z
0x14000cd2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd31  cmp     byte ptr [rbx+0A5h], 0
0x14000cd38  jnz     short loc_14000CD7A
0x14000cd3a  cmp     byte ptr [rbx+0A6h], 0
0x14000cd41  jnz     short loc_14000CD7A
0x14000cd43  mov     rcx, [rbx+300h]; hHandle
0x14000cd4a  xor     edx, edx; dwMilliseconds
0x14000cd4c  call    cs:__imp_WaitForSingleObject
0x14000cd52  cmp     eax, 102h
0x14000cd57  jnz     short loc_14000CD73
0x14000cd59  mov     rcx, [rbx+2F8h]; hHandle
0x14000cd60  xor     edx, edx; dwMilliseconds
0x14000cd62  call    cs:__imp_WaitForSingleObject
0x14000cd68  cmp     eax, 102h
0x14000cd6d  jz      loc_14000CE28
0x14000cd73  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cd7a  cmp     rcx, r14
0x14000cd7d  jz      short loc_14000CDAE
0x14000cd7f  test    byte ptr [rcx+1Ch], 1
0x14000cd83  jz      short loc_14000CDAE
0x14000cd85  cmp     byte ptr [rcx+19h], 5
0x14000cd89  jb      short loc_14000CDAE
0x14000cd8b  mov     rcx, [rcx+10h]
0x14000cd8f  lea     r9, [rbx+2A0h]
0x14000cd96  mov     edx, 0FCh
0x14000cd9b  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000cda2  call    WPP_SF_Z
0x14000cda7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cdae  cmp     dword ptr [rbx+2C8h], 0
0x14000cdb5  jnz     short loc_14000CDF3
0x14000cdb7  cmp     rcx, r14
0x14000cdba  jz      short loc_14000CDE4
0x14000cdbc  test    byte ptr [rcx+1Ch], 1
0x14000cdc0  jz      short loc_14000CDE4
0x14000cdc2  cmp     byte ptr [rcx+19h], 4
0x14000cdc6  jb      short loc_14000CDE4
0x14000cdc8  mov     rcx, [rcx+10h]
0x14000cdcc  lea     r9, [rbx+90h]
0x14000cdd3  mov     edx, 85h
0x14000cdd8  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000cddf  call    WPP_SF_Z
0x14000cde4  mov     rcx, [rbx+308h]; hEvent
0x14000cdeb  call    cs:__imp_SetEvent
0x14000cdf1  jmp     short loc_14000CE28
0x14000cdf3  cmp     rcx, r14
0x14000cdf6  jz      short loc_14000CE28
0x14000cdf8  test    byte ptr [rcx+1Ch], 1
0x14000cdfc  jz      short loc_14000CE28
0x14000cdfe  cmp     byte ptr [rcx+19h], 4
0x14000ce02  jb      short loc_14000CE28
0x14000ce04  mov     rcx, [rcx+10h]
0x14000ce08  lea     rax, [rbx+90h]
0x14000ce0f  mov     edx, 86h
0x14000ce14  mov     [rsp+58h+var_38], rax
0x14000ce19  mov     r9d, esi
0x14000ce1c  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000ce23  call    WPP_SF_dZ
0x14000ce28  test    rdi, rdi
0x14000ce2b  jz      short loc_14000CE36
0x14000ce2d  mov     rcx, rdi; SRWLock
0x14000ce30  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ce36  add     rsp, 38h
0x14000ce3a  pop     r14
0x14000ce3c  pop     rdi
0x14000ce3d  pop     rsi
0x14000ce3e  pop     rbx
0x14000ce3f  retn
```
