# Apx::ApfStream::WriteData(void *,ulong)

- ea: `0x18001a2c0`
- end: `0x18001a429`
- name: `?WriteData@ApfStream@Apx@@QEAAJPEAXK@Z`
- size: `361`
- prototype: `__int64 __fastcall(Apx::ApfStream *this, char *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001aaf0`

## callees

- `0x18000a12c`
- `0x18001a2c0`
- `0x180029880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a392`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a39c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a39c`

## pseudocode

```c
__int64 __fastcall Apx::ApfStream::WriteData(Apx::ApfStream *this, char *a2, unsigned int a3)
{
  unsigned int v5; // edi
  __int64 v6; // r14
  unsigned int v7; // esi
  int v8; // ebp
  int v9; // ecx
  unsigned int v10; // r15d
  int v11; // r13d
  unsigned int v12; // edx
  unsigned int v13; // ecx
  unsigned int v14; // eax
  __int64 v15; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids);
  }
  v5 = a3;
  v6 = *((_QWORD *)this + 20) + *((unsigned int *)this + 42);
  v7 = *((_DWORD *)this + 66);
  v8 = 0;
  do
  {
    v9 = *((_DWORD *)this + 67);
    v10 = *((_DWORD *)this + 68) - v7;
    if ( v10 >= v5 )
      v10 = v5;
    v11 = v9 * v10;
    memcpy_0((void *)(v6 + v7 * v9), &a2[v8], v9 * v10);
    v12 = (v10 + v7) % *((_DWORD *)this + 68);
    v13 = v7;
    v7 = v12;
    if ( v13 >= v12 || (v14 = *((_DWORD *)this + 69), v13 < v14) && v12 >= v14 )
    {
      if ( !SetEvent(*((HANDLE *)this + 18)) )
        GetLastError();
    }
    v8 += v11;
    v5 -= v10;
  }
  while ( v5 );
  v15 = *((_QWORD *)this + 22);
  *((_DWORD *)this + 66) = v7;
  _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
  *(_QWORD *)(*((_QWORD *)this + 22) + 16LL) += a3;
  *(_QWORD *)(*((_QWORD *)this + 22) + 24LL) += a3;
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 22) + 12LL));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18001a2c0  mov     [rsp+arg_0], rbx
0x18001a2c5  mov     [rsp+arg_10], r8d
0x18001a2ca  mov     [rsp+arg_8], rdx
0x18001a2cf  push    rbp
0x18001a2d0  push    rsi
0x18001a2d1  push    rdi
0x18001a2d2  push    r12
0x18001a2d4  push    r13
0x18001a2d6  push    r14
0x18001a2d8  push    r15
0x18001a2da  sub     rsp, 20h
0x18001a2de  mov     r12d, r8d
0x18001a2e1  mov     rbx, rcx
0x18001a2e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2eb  lea     rax, WPP_GLOBAL_Control
0x18001a2f2  cmp     rcx, rax
0x18001a2f5  jz      short loc_18001A318
0x18001a2f7  test    byte ptr [rcx+1Ch], 1
0x18001a2fb  jz      short loc_18001A318
0x18001a2fd  cmp     byte ptr [rcx+19h], 5
0x18001a301  jb      short loc_18001A318
0x18001a303  mov     rcx, [rcx+10h]
0x18001a307  lea     r8, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids
0x18001a30e  mov     edx, 18h
0x18001a313  call    WPP_SF_
0x18001a318  mov     r14d, [rbx+0A8h]
0x18001a31f  mov     edi, r12d
0x18001a322  add     r14, [rbx+0A0h]
0x18001a329  mov     esi, [rbx+108h]
0x18001a32f  xor     ebp, ebp
0x18001a331  mov     r12, [rsp+58h+arg_8]
0x18001a336  mov     ecx, [rbx+10Ch]
0x18001a33c  mov     r15d, [rbx+110h]
0x18001a343  sub     r15d, esi
0x18001a346  mov     edx, ebp
0x18001a348  cmp     r15d, edi
0x18001a34b  cmovnb  r15d, edi
0x18001a34f  add     rdx, r12; Src
0x18001a352  mov     eax, r15d
0x18001a355  imul    eax, ecx
0x18001a358  imul    ecx, esi
0x18001a35b  mov     r8d, eax; Size
0x18001a35e  add     rcx, r14; void *
0x18001a361  mov     r13d, eax
0x18001a364  call    memcpy_0
0x18001a369  lea     eax, [r15+rsi]
0x18001a36d  xor     edx, edx
0x18001a36f  div     dword ptr [rbx+110h]
0x18001a375  mov     ecx, esi
0x18001a377  mov     esi, edx
0x18001a379  cmp     ecx, edx
0x18001a37b  jnb     short loc_18001A38B
0x18001a37d  mov     eax, [rbx+114h]
0x18001a383  cmp     ecx, eax
0x18001a385  jnb     short loc_18001A3A2
0x18001a387  cmp     edx, eax
0x18001a389  jb      short loc_18001A3A2
0x18001a38b  mov     rcx, [rbx+90h]; hEvent
0x18001a392  call    cs:__imp_SetEvent
0x18001a398  test    eax, eax
0x18001a39a  jnz     short loc_18001A3A2
0x18001a39c  call    cs:__imp_GetLastError
0x18001a3a2  add     ebp, r13d
0x18001a3a5  sub     edi, r15d
0x18001a3a8  jnz     short loc_18001A336
0x18001a3aa  mov     rax, [rbx+0B0h]
0x18001a3b1  mov     [rbx+108h], esi
0x18001a3b7  lock inc dword ptr [rax+8]
0x18001a3bb  mov     rax, [rbx+0B0h]
0x18001a3c2  mov     ecx, [rsp+58h+arg_10]
0x18001a3c6  add     [rax+10h], rcx
0x18001a3ca  mov     rax, [rbx+0B0h]
0x18001a3d1  add     [rax+18h], rcx
0x18001a3d5  mov     rax, [rbx+0B0h]
0x18001a3dc  lock inc dword ptr [rax+0Ch]
0x18001a3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3e7  lea     rax, WPP_GLOBAL_Control
0x18001a3ee  cmp     rcx, rax
0x18001a3f1  jz      short loc_18001A412
0x18001a3f3  test    byte ptr [rcx+1Ch], 1
0x18001a3f7  jz      short loc_18001A412
0x18001a3f9  cmp     byte ptr [rcx+19h], 5
0x18001a3fd  jb      short loc_18001A412
0x18001a3ff  mov     rcx, [rcx+10h]
0x18001a403  lea     edx, [rdi+19h]
0x18001a406  lea     r8, WPP_95f14fe00a043d1e0a2a39e30ffc9023_Traceguids
0x18001a40d  call    WPP_SF_
0x18001a412  mov     rbx, [rsp+58h+arg_0]
0x18001a417  xor     eax, eax
0x18001a419  add     rsp, 20h
0x18001a41d  pop     r15
0x18001a41f  pop     r14
0x18001a421  pop     r13
0x18001a423  pop     r12
0x18001a425  pop     rdi
0x18001a426  pop     rsi
0x18001a427  pop     rbp
0x18001a428  retn
```
