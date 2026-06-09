# GameInputDevice::Create(ISIPCEndpoint *,unsigned __int64,void *,GameInputDevice * *)

- ea: `0x180004c30`
- end: `0x180004ee5`
- name: `?Create@GameInputDevice@@SAJPEAUISIPCEndpoint@@_KPEAXPEAPEAV1@@Z`
- size: `693`
- prototype: `__int64 __fastcall(struct ISIPCEndpoint *, unsigned __int64, void *, struct GameInputDevice **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180009050`

## callees

- `0x180001304`
- `0x180004050`
- `0x180004990`
- `0x180004c30`
- `0x18000a91c`
- `0x18000c11c`
- `0x18004c8a5`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180004c65`
- `ntdll!RtlAllocateHeap` at `0x180004c65`

## pseudocode

```c
__int64 __fastcall GameInputDevice::Create(
        struct ISIPCEndpoint *a1,
        unsigned __int64 a2,
        void *a3,
        struct GameInputDevice **a4)
{
  char *Heap; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  char *v11; // rbx
  int v12; // edi
  int v13; // eax
  const struct std::nothrow_t *v14; // rdx
  _OWORD *v16; // rcx
  __int64 v17; // rdx
  _OWORD *v18; // rax
  __int128 v19; // xmm1
  unsigned __int64 i; // r9
  unsigned __int8 v21; // al
  int v22; // [rsp+40h] [rbp-48h] BYREF
  __int64 *v23[8]; // [rsp+48h] [rbp-40h] BYREF
  int v24; // [rsp+A8h] [rbp+20h] BYREF

  *a4 = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x420u);
  v11 = Heap;
  if ( Heap )
  {
    *((_DWORD *)Heap + 2) = 0;
    *((_QWORD *)Heap + 2) = 0;
    *((_QWORD *)Heap + 3) = 0;
    *(_QWORD *)Heap = &GameInputDevice::`vftable';
    *((_QWORD *)Heap + 4) = 0;
    *((_DWORD *)Heap + 16) = 0;
    *((_QWORD *)Heap + 7) = Heap + 48;
    *((_QWORD *)Heap + 6) = Heap + 48;
    *((_QWORD *)Heap + 5) = 0;
    *((_QWORD *)Heap + 9) = 0;
    *((_QWORD *)Heap + 10) = 0;
    *(_OWORD *)(Heap + 904) = 0;
    *(_OWORD *)(Heap + 88) = 0;
    memset_0(Heap + 104, 0, 0x190u);
    memset_0(v11 + 504, 0, 0x190u);
    memset_0(v11 + 920, 0, 0x82u);
    v12 = GameInputDevice::ReplaceBuffer((GameInputDevice *)v11, a1, a2, a3, 0);
    if ( v12 < 0 )
    {
LABEL_5:
      GameInputDevice::~GameInputDevice((GameInputDevice *)v11);
      operator delete(v11, v14);
      return (unsigned int)v12;
    }
    v13 = FeedbackStateCache::Create((struct GameInputDevice *)v11, (struct FeedbackStateCache **)v11 + 5);
    if ( v13 < 0 )
    {
      v12 = v13;
      goto LABEL_5;
    }
    v16 = *(_OWORD **)(*((_QWORD *)v11 + 3) + 88LL);
    if ( v16 )
    {
      v17 = 6;
      v18 = v11 + 88;
      do
      {
        *v18 = *v16;
        v18[1] = v16[1];
        v18[2] = v16[2];
        v18[3] = v16[3];
        v18[4] = v16[4];
        v18[5] = v16[5];
        v18[6] = v16[6];
        v19 = v16[7];
        v16 += 8;
        v18[7] = v19;
        v18 += 8;
        --v17;
      }
      while ( v17 );
      *v18 = *v16;
      v18[1] = v16[1];
      v18[2] = v16[2];
      v18[3] = v16[3];
    }
    memset_0(v11 + 920, 0, 0x82u);
    for ( i = 0; i < 0x20; ++i )
    {
      v21 = *(_BYTE *)(i + *((_QWORD *)v11 + 4) + 32);
      *(_WORD *)&v11[4 * i + 920] = (v21 >> 4) + ((unsigned __int8)(v21 >> 4) < 0xAu ? 48 : 55);
      *(_WORD *)&v11[4 * i + 922] = (v21 & 0xF) + ((v21 & 0xFu) < 0xA ? 48 : 55);
    }
    *a4 = (struct GameInputDevice *)v11;
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      v24 = -2147024882;
      v23[0] = (__int64 *)"onecore\\xbox\\gameinput\\client\\GameInputDevice.cpp";
      v22 = 33;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v23,
        (unsigned __int8 *)byte_180059D25,
        v9,
        v10,
        v23,
        (__int64)&v22,
        (__int64)&v24);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180004c30  push    rbx
0x180004c32  push    rbp
0x180004c33  push    rsi
0x180004c34  push    rdi
0x180004c35  push    r14
0x180004c37  push    r15
0x180004c39  sub     rsp, 58h
0x180004c3d  mov     r14, rcx
0x180004c40  mov     qword ptr [r9], 0
0x180004c47  mov     rcx, gs:60h
0x180004c50  mov     rdi, r8
0x180004c53  mov     rbp, rdx
0x180004c56  mov     r8d, 420h; Size
0x180004c5c  xor     edx, edx; Flags
0x180004c5e  mov     rsi, r9
0x180004c61  mov     rcx, [rcx+30h]; HeapHandle
0x180004c65  call    cs:__imp_RtlAllocateHeap
0x180004c6c  nop     dword ptr [rax+rax+00h]
0x180004c71  mov     rbx, rax
0x180004c74  test    rax, rax
0x180004c77  jz      loc_180004E60
0x180004c7d  mov     dword ptr [rax+8], 0
0x180004c84  lea     rcx, [rbx+68h]; void *
0x180004c88  mov     qword ptr [rax+10h], 0
0x180004c90  xorps   xmm0, xmm0
0x180004c93  mov     qword ptr [rbx+18h], 0
0x180004c9b  lea     rax, ??_7GameInputDevice@@6B@; const GameInputDevice::`vftable'
0x180004ca2  mov     [rbx], rax
0x180004ca5  xorps   xmm1, xmm1
0x180004ca8  lea     rax, [rbx+30h]
0x180004cac  mov     qword ptr [rbx+20h], 0
0x180004cb4  mov     dword ptr [rax+10h], 0
0x180004cbb  mov     r15d, 190h
0x180004cc1  mov     [rax+8], rax
0x180004cc5  mov     r8d, r15d; Size
0x180004cc8  mov     [rax], rax
0x180004ccb  xor     edx, edx; Val
0x180004ccd  mov     qword ptr [rbx+28h], 0
0x180004cd5  mov     qword ptr [rbx+48h], 0
0x180004cdd  mov     qword ptr [rbx+50h], 0
0x180004ce5  movups  xmmword ptr [rbx+388h], xmm0
0x180004cec  movups  xmmword ptr [rbx+58h], xmm1
0x180004cf0  call    memset_0
0x180004cf5  lea     rcx, [rbx+1F8h]; void *
0x180004cfc  mov     r8d, r15d; Size
0x180004cff  xor     edx, edx; Val
0x180004d01  call    memset_0
0x180004d06  mov     r15d, 82h
0x180004d0c  lea     rcx, [rbx+398h]; void *
0x180004d13  mov     r8d, r15d; Size
0x180004d16  xor     edx, edx; Val
0x180004d18  call    memset_0
0x180004d1d  mov     r9, rdi; void *
0x180004d20  mov     [rsp+88h+var_68], 0; void *
0x180004d29  mov     r8, rbp; unsigned __int64
0x180004d2c  mov     rdx, r14; struct ISIPCEndpoint *
0x180004d2f  mov     rcx, rbx; this
0x180004d32  call    ?ReplaceBuffer@GameInputDevice@@QEAAJPEAUISIPCEndpoint@@_KPEAXPEBX@Z; GameInputDevice::ReplaceBuffer(ISIPCEndpoint *,unsigned __int64,void *,void const *)
0x180004d37  mov     edi, eax
0x180004d39  test    eax, eax
0x180004d3b  js      short loc_180004D4F
0x180004d3d  lea     rdx, [rbx+28h]; struct FeedbackStateCache **
0x180004d41  mov     rcx, rbx; struct GameInputDevice *
0x180004d44  call    ?Create@FeedbackStateCache@@SAJPEAVGameInputDevice@@PEAPEAV1@@Z; FeedbackStateCache::Create(GameInputDevice *,FeedbackStateCache * *)
0x180004d49  test    eax, eax
0x180004d4b  jns     short loc_180004D66
0x180004d4d  mov     edi, eax
0x180004d4f  mov     rcx, rbx; this
0x180004d52  call    ??1GameInputDevice@@UEAA@XZ; GameInputDevice::~GameInputDevice(void)
0x180004d57  mov     rcx, rbx; P
0x180004d5a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180004d5f  mov     eax, edi
0x180004d61  jmp     loc_180004ED7
0x180004d66  mov     rax, [rbx+18h]
0x180004d6a  nop
0x180004d6b  mov     rcx, [rax+58h]
0x180004d6f  test    rcx, rcx
0x180004d72  jz      short loc_180004DE9
0x180004d74  mov     edx, 6
0x180004d79  lea     rax, [rbx+58h]
0x180004d7d  lea     r9d, [rdx+7Ah]
0x180004d81  movups  xmm0, xmmword ptr [rcx]
0x180004d84  movups  xmmword ptr [rax], xmm0
0x180004d87  movups  xmm1, xmmword ptr [rcx+10h]
0x180004d8b  movups  xmmword ptr [rax+10h], xmm1
0x180004d8f  movups  xmm0, xmmword ptr [rcx+20h]
0x180004d93  movups  xmmword ptr [rax+20h], xmm0
0x180004d97  movups  xmm1, xmmword ptr [rcx+30h]
0x180004d9b  movups  xmmword ptr [rax+30h], xmm1
0x180004d9f  movups  xmm0, xmmword ptr [rcx+40h]
0x180004da3  movups  xmmword ptr [rax+40h], xmm0
0x180004da7  movups  xmm1, xmmword ptr [rcx+50h]
0x180004dab  movups  xmmword ptr [rax+50h], xmm1
0x180004daf  movups  xmm0, xmmword ptr [rcx+60h]
0x180004db3  movups  xmmword ptr [rax+60h], xmm0
0x180004db7  movups  xmm1, xmmword ptr [rcx+70h]
0x180004dbb  add     rcx, r9
0x180004dbe  movups  xmmword ptr [rax+70h], xmm1
0x180004dc2  add     rax, r9
0x180004dc5  sub     rdx, 1
0x180004dc9  jnz     short loc_180004D81
0x180004dcb  movups  xmm0, xmmword ptr [rcx]
0x180004dce  movups  xmmword ptr [rax], xmm0
0x180004dd1  movups  xmm1, xmmword ptr [rcx+10h]
0x180004dd5  movups  xmmword ptr [rax+10h], xmm1
0x180004dd9  movups  xmm0, xmmword ptr [rcx+20h]
0x180004ddd  movups  xmmword ptr [rax+20h], xmm0
0x180004de1  movups  xmm1, xmmword ptr [rcx+30h]
0x180004de5  movups  xmmword ptr [rax+30h], xmm1
0x180004de9  lea     rcx, [rbx+398h]; void *
0x180004df0  mov     r8, r15; Size
0x180004df3  xor     edx, edx; Val
0x180004df5  call    memset_0
0x180004dfa  xor     r9d, r9d
0x180004dfd  mov     r10w, 0FFF9h
0x180004e02  mov     rax, [rbx+20h]
0x180004e06  mov     cl, [r9+rax+20h]
0x180004e0b  mov     al, cl
0x180004e0d  and     cl, 0Fh
0x180004e10  shr     al, 4
0x180004e13  movzx   edx, al
0x180004e16  cmp     dl, 0Ah
0x180004e19  movzx   r8d, cl
0x180004e1d  sbb     ax, ax
0x180004e20  and     ax, r10w
0x180004e24  add     ax, 37h ; '7'
0x180004e28  add     ax, dx
0x180004e2b  mov     [rbx+r9*4+398h], ax
0x180004e34  cmp     r8b, 0Ah
0x180004e38  sbb     ax, ax
0x180004e3b  and     ax, r10w
0x180004e3f  add     ax, 37h ; '7'
0x180004e43  add     ax, r8w
0x180004e47  mov     [rbx+r9*4+39Ah], ax
0x180004e50  inc     r9
0x180004e53  cmp     r9, 20h ; ' '
0x180004e57  jb      short loc_180004E02
0x180004e59  mov     [rsi], rbx
0x180004e5c  xor     eax, eax
0x180004e5e  jmp     short loc_180004ED7
0x180004e60  mov     eax, cs:dword_180069000
0x180004e66  mov     ebx, 8007000Eh
0x180004e6b  cmp     eax, 2
0x180004e6e  jbe     short loc_180004ED5
0x180004e70  mov     rcx, cs:qword_180069018
0x180004e77  mov     rax, cs:qword_180069010
0x180004e7e  test    al, 1
0x180004e80  jz      short loc_180004ED5
0x180004e82  mov     rax, rcx
0x180004e85  and     eax, 1
0x180004e88  cmp     rax, rcx
0x180004e8b  jnz     short loc_180004ED5
0x180004e8d  lea     rcx, aOnecoreXboxGam_49; "onecore\\xbox\\gameinput\\client\\GameI"...
0x180004e94  mov     [rsp+88h+arg_18], ebx
0x180004e9b  mov     [rsp+88h+var_40], rcx
0x180004ea0  lea     rdx, byte_180059D25
0x180004ea7  lea     rcx, [rsp+88h+arg_18]
0x180004eaf  mov     [rsp+88h+var_48], 21h ; '!'
0x180004eb7  mov     [rsp+88h+var_58], rcx
0x180004ebc  lea     rcx, [rsp+88h+var_48]
0x180004ec1  mov     [rsp+88h+var_60], rcx
0x180004ec6  lea     rcx, [rsp+88h+var_40]
0x180004ecb  mov     [rsp+88h+var_68], rcx
0x180004ed0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180004ed5  mov     eax, ebx
0x180004ed7  add     rsp, 58h
0x180004edb  pop     r15
0x180004edd  pop     r14
0x180004edf  pop     rdi
0x180004ee0  pop     rsi
0x180004ee1  pop     rbp
0x180004ee2  pop     rbx
0x180004ee3  retn
```
