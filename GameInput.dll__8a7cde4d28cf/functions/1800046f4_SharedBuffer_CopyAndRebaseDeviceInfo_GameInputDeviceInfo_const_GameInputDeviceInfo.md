# SharedBuffer::CopyAndRebaseDeviceInfo(GameInputDeviceInfo const *,GameInputDeviceInfo * *)

- ea: `0x1800046f4`
- end: `0x180004989`
- name: `?CopyAndRebaseDeviceInfo@SharedBuffer@@CAJPEBUGameInputDeviceInfo@@PEAPEAU2@@Z`
- size: `661`
- prototype: `__int64 __fastcall(const struct GameInputDeviceInfo *Src, struct GameInputDeviceInfo **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180005200`

## callees

- `0x180001304`
- `0x1800046f4`
- `0x18004c88d`
- `0x18004c8a5`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000471b`
- `ntdll!RtlAllocateHeap` at `0x18000471b`

## pseudocode

```c
__int64 __fastcall SharedBuffer::CopyAndRebaseDeviceInfo(
        const struct GameInputDeviceInfo *Src,
        struct GameInputDeviceInfo **a2)
{
  _QWORD *Heap; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  void *v7; // rbx
  __int64 result; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  int v29; // [rsp+60h] [rbp+8h] BYREF
  int v30; // [rsp+68h] [rbp+10h] BYREF
  const char *v31; // [rsp+70h] [rbp+18h] BYREF

  *a2 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, *(unsigned int *)Src);
  v7 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0x148u);
    memcpy_0(v7, Src, *(unsigned int *)Src);
    v9 = *((_QWORD *)v7 + 20);
    if ( v9 )
      v9 += (__int64)v7;
    *((_QWORD *)v7 + 20) = v9;
    v10 = *((_QWORD *)v7 + 21);
    if ( v10 )
      v10 += (__int64)v7;
    *((_QWORD *)v7 + 21) = v10;
    v11 = *((_QWORD *)v7 + 22);
    if ( v11 )
      v11 += (__int64)v7;
    *((_QWORD *)v7 + 22) = v11;
    v12 = *((_QWORD *)v7 + 23);
    if ( v12 )
      v12 += (__int64)v7;
    *((_QWORD *)v7 + 23) = v12;
    v13 = *((_QWORD *)v7 + 24);
    if ( v13 )
      v13 += (__int64)v7;
    *((_QWORD *)v7 + 24) = v13;
    v14 = *((_QWORD *)v7 + 25);
    if ( v14 )
      v14 += (__int64)v7;
    *((_QWORD *)v7 + 25) = v14;
    v15 = *((_QWORD *)v7 + 26);
    if ( v15 )
      v15 += (__int64)v7;
    *((_QWORD *)v7 + 26) = v15;
    v16 = *((_QWORD *)v7 + 27);
    if ( v16 )
      v16 += (__int64)v7;
    *((_QWORD *)v7 + 27) = v16;
    v17 = *((_QWORD *)v7 + 28);
    if ( v17 )
      v17 += (__int64)v7;
    *((_QWORD *)v7 + 28) = v17;
    v18 = *((_QWORD *)v7 + 29);
    if ( v18 )
      v18 += (__int64)v7;
    *((_QWORD *)v7 + 29) = v18;
    v19 = *((_QWORD *)v7 + 30);
    if ( v19 )
      v19 += (__int64)v7;
    *((_QWORD *)v7 + 30) = v19;
    v20 = *((_QWORD *)v7 + 31);
    if ( v20 )
      v20 += (__int64)v7;
    *((_QWORD *)v7 + 31) = v20;
    v21 = *((_QWORD *)v7 + 32);
    if ( v21 )
      v21 += (__int64)v7;
    *((_QWORD *)v7 + 32) = v21;
    v22 = *((_QWORD *)v7 + 33);
    if ( v22 )
      v22 += (__int64)v7;
    *((_QWORD *)v7 + 33) = v22;
    v23 = *((_QWORD *)v7 + 34);
    if ( v23 )
      v23 += (__int64)v7;
    *((_QWORD *)v7 + 34) = v23;
    v24 = *((_QWORD *)v7 + 35);
    if ( v24 )
      v24 += (__int64)v7;
    *((_QWORD *)v7 + 35) = v24;
    v25 = *((_QWORD *)v7 + 36);
    if ( v25 )
      v25 += (__int64)v7;
    *((_QWORD *)v7 + 36) = v25;
    v26 = *((_QWORD *)v7 + 37);
    if ( v26 )
      v26 += (__int64)v7;
    *((_QWORD *)v7 + 37) = v26;
    v27 = *((_QWORD *)v7 + 38);
    if ( v27 )
      v27 += (__int64)v7;
    *((_QWORD *)v7 + 38) = v27;
    v28 = *((_QWORD *)v7 + 39);
    if ( v28 )
      v28 += (__int64)v7;
    *((_QWORD *)v7 + 39) = v28;
    result = 0;
    *a2 = (struct GameInputDeviceInfo *)v7;
  }
  else
  {
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      v29 = -2147024882;
      v31 = "onecore\\xbox\\gameinput\\client\\SharedBuffer.cpp";
      v30 = 349;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)&v31,
        (unsigned __int8 *)&unk_1800595C8,
        v5,
        v6,
        (__int64 **)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800046f4  push    rbx
0x1800046f6  push    rsi
0x1800046f7  push    rdi
0x1800046f8  sub     rsp, 40h
0x1800046fc  mov     qword ptr [rdx], 0
0x180004703  mov     rdi, rcx
0x180004706  mov     r8d, [rcx]; Size
0x180004709  mov     rsi, rdx
0x18000470c  mov     rcx, gs:60h
0x180004715  xor     edx, edx; Flags
0x180004717  mov     rcx, [rcx+30h]; HeapHandle
0x18000471b  call    cs:__imp_RtlAllocateHeap
0x180004722  nop     dword ptr [rax+rax+00h]
0x180004727  mov     rbx, rax
0x18000472a  test    rax, rax
0x18000472d  jnz     short loc_1800047A5
0x18000472f  mov     eax, cs:dword_180069000
0x180004735  mov     ebx, 8007000Eh
0x18000473a  cmp     eax, 2
0x18000473d  jbe     short loc_18000479E
0x18000473f  mov     rcx, cs:qword_180069018
0x180004746  mov     rax, cs:qword_180069010
0x18000474d  test    al, 1
0x18000474f  jz      short loc_18000479E
0x180004751  mov     rax, rcx
0x180004754  and     eax, 1
0x180004757  cmp     rax, rcx
0x18000475a  jnz     short loc_18000479E
0x18000475c  lea     rcx, aOnecoreXboxGam_20; "onecore\\xbox\\gameinput\\client\\Share"...
0x180004763  mov     [rsp+58h+arg_0], ebx
0x180004767  mov     [rsp+58h+arg_10], rcx
0x18000476c  lea     rdx, unk_1800595C8
0x180004773  lea     rcx, [rsp+58h+arg_0]
0x180004778  mov     [rsp+58h+arg_8], 15Dh
0x180004780  mov     [rsp+58h+var_28], rcx
0x180004785  lea     rcx, [rsp+58h+arg_8]
0x18000478a  mov     [rsp+58h+var_30], rcx
0x18000478f  lea     rcx, [rsp+58h+arg_10]
0x180004794  mov     [rsp+58h+var_38], rcx
0x180004799  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000479e  mov     eax, ebx
0x1800047a0  jmp     loc_180004980
0x1800047a5  xor     edx, edx; Val
0x1800047a7  mov     r8d, 148h; Size
0x1800047ad  mov     rcx, rbx; void *
0x1800047b0  call    memset_0
0x1800047b5  mov     r8d, [rdi]; Size
0x1800047b8  mov     rdx, rdi; Src
0x1800047bb  mov     rcx, rbx; void *
0x1800047be  call    memcpy_0
0x1800047c3  mov     rax, [rbx+0A0h]
0x1800047ca  test    rax, rax
0x1800047cd  jz      short loc_1800047D2
0x1800047cf  add     rax, rbx
0x1800047d2  mov     [rbx+0A0h], rax
0x1800047d9  mov     rax, [rbx+0A8h]
0x1800047e0  test    rax, rax
0x1800047e3  jz      short loc_1800047E8
0x1800047e5  add     rax, rbx
0x1800047e8  mov     [rbx+0A8h], rax
0x1800047ef  mov     rax, [rbx+0B0h]
0x1800047f6  test    rax, rax
0x1800047f9  jz      short loc_1800047FE
0x1800047fb  add     rax, rbx
0x1800047fe  mov     [rbx+0B0h], rax
0x180004805  mov     rax, [rbx+0B8h]
0x18000480c  test    rax, rax
0x18000480f  jz      short loc_180004814
0x180004811  add     rax, rbx
0x180004814  mov     [rbx+0B8h], rax
0x18000481b  mov     rax, [rbx+0C0h]
0x180004822  test    rax, rax
0x180004825  jz      short loc_18000482A
0x180004827  add     rax, rbx
0x18000482a  mov     [rbx+0C0h], rax
0x180004831  mov     rax, [rbx+0C8h]
0x180004838  test    rax, rax
0x18000483b  jz      short loc_180004840
0x18000483d  add     rax, rbx
0x180004840  mov     [rbx+0C8h], rax
0x180004847  mov     rax, [rbx+0D0h]
0x18000484e  test    rax, rax
0x180004851  jz      short loc_180004856
0x180004853  add     rax, rbx
0x180004856  mov     [rbx+0D0h], rax
0x18000485d  mov     rax, [rbx+0D8h]
0x180004864  test    rax, rax
0x180004867  jz      short loc_18000486C
0x180004869  add     rax, rbx
0x18000486c  mov     [rbx+0D8h], rax
0x180004873  mov     rax, [rbx+0E0h]
0x18000487a  test    rax, rax
0x18000487d  jz      short loc_180004882
0x18000487f  add     rax, rbx
0x180004882  mov     [rbx+0E0h], rax
0x180004889  mov     rax, [rbx+0E8h]
0x180004890  test    rax, rax
0x180004893  jz      short loc_180004898
0x180004895  add     rax, rbx
0x180004898  mov     [rbx+0E8h], rax
0x18000489f  mov     rax, [rbx+0F0h]
0x1800048a6  test    rax, rax
0x1800048a9  jz      short loc_1800048AE
0x1800048ab  add     rax, rbx
0x1800048ae  mov     [rbx+0F0h], rax
0x1800048b5  mov     rax, [rbx+0F8h]
0x1800048bc  test    rax, rax
0x1800048bf  jz      short loc_1800048C4
0x1800048c1  add     rax, rbx
0x1800048c4  mov     [rbx+0F8h], rax
0x1800048cb  mov     rax, [rbx+100h]
0x1800048d2  test    rax, rax
0x1800048d5  jz      short loc_1800048DA
0x1800048d7  add     rax, rbx
0x1800048da  mov     [rbx+100h], rax
0x1800048e1  mov     rax, [rbx+108h]
0x1800048e8  test    rax, rax
0x1800048eb  jz      short loc_1800048F0
0x1800048ed  add     rax, rbx
0x1800048f0  mov     [rbx+108h], rax
0x1800048f7  mov     rax, [rbx+110h]
0x1800048fe  test    rax, rax
0x180004901  jz      short loc_180004906
0x180004903  add     rax, rbx
0x180004906  mov     [rbx+110h], rax
0x18000490d  mov     rax, [rbx+118h]
0x180004914  test    rax, rax
0x180004917  jz      short loc_18000491C
0x180004919  add     rax, rbx
0x18000491c  mov     [rbx+118h], rax
0x180004923  mov     rax, [rbx+120h]
0x18000492a  test    rax, rax
0x18000492d  jz      short loc_180004932
0x18000492f  add     rax, rbx
0x180004932  mov     [rbx+120h], rax
0x180004939  mov     rax, [rbx+128h]
0x180004940  test    rax, rax
0x180004943  jz      short loc_180004948
0x180004945  add     rax, rbx
0x180004948  mov     [rbx+128h], rax
0x18000494f  mov     rax, [rbx+130h]
0x180004956  test    rax, rax
0x180004959  jz      short loc_18000495E
0x18000495b  add     rax, rbx
0x18000495e  mov     [rbx+130h], rax
0x180004965  mov     rax, [rbx+138h]
0x18000496c  test    rax, rax
0x18000496f  jz      short loc_180004974
0x180004971  add     rax, rbx
0x180004974  mov     [rbx+138h], rax
0x18000497b  xor     eax, eax
0x18000497d  mov     [rsi], rbx
0x180004980  add     rsp, 40h
0x180004984  pop     rdi
0x180004985  pop     rsi
0x180004986  pop     rbx
0x180004987  retn
```
