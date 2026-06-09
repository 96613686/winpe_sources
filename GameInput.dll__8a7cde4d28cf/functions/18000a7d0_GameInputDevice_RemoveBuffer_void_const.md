# GameInputDevice::RemoveBuffer(void const *)

- ea: `0x18000a7d0`
- end: `0x18000a914`
- name: `?RemoveBuffer@GameInputDevice@@QEAAXPEBX@Z`
- size: `324`
- prototype: `void __fastcall(GameInputDevice *__hidden this, const void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180009050`
- `0x18000a91c`

## callees

- `0x18000120c`
- `0x180008550`
- `0x18000a7d0`
- `0x18000d68c`

## pseudocode

```c
void __fastcall GameInputDevice::RemoveBuffer(GameInputDevice *this, const void *a2)
{
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // [rsp+50h] [rbp-28h] BYREF
  const char *v11; // [rsp+58h] [rbp-20h] BYREF
  const char *v12; // [rsp+60h] [rbp-18h] BYREF
  __int16 v13; // [rsp+90h] [rbp+18h] BYREF
  __int16 v14; // [rsp+98h] [rbp+20h] BYREF

  if ( !GameInputDispatcher::IsDispatchThread() )
  {
    GameInputFailFast(2147549183LL, 137);
    JUMPOUT(0x18000A913LL);
  }
  v6 = *((_QWORD *)this + 3);
  if ( v6 && *(const void **)(v6 + 112) == a2 )
  {
    *((_QWORD *)this + 3) = 0;
    _mm_mfence();
    v7 = (_QWORD *)((char *)this + 48);
    v8 = *((_QWORD *)this + 6);
    if ( *(GameInputDevice **)(v8 + 8) != (GameInputDevice *)((char *)this + 48) )
      __fastfail(3u);
    *(_QWORD *)v6 = v8;
    *(_QWORD *)(v6 + 8) = v7;
    *(_QWORD *)(v8 + 8) = v6;
    ++*((_DWORD *)this + 16);
    *v7 = v6;
    *((_DWORD *)this + 20) = 0;
    _mm_mfence();
    if ( (unsigned int)dword_180069000 > 4 && (qword_180069010 & 1) != 0 && (qword_180069018 & 1) == qword_180069018 )
    {
      v9 = *((_QWORD *)this + 4);
      v13 = *(_WORD *)(v9 + 6);
      v14 = *(_WORD *)(v9 + 4);
      v11 = "Device disconnected";
      v12 = "onecore\\xbox\\gameinput\\client\\GameInputDevice.cpp";
      v10 = 150;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(
        v9,
        (unsigned int)qword_180059668,
        v4,
        v5,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v11,
        (__int64)&v14,
        (__int64)&v13);
    }
  }
}

```

## disassembly

```asm
0x18000a7d0  mov     [rsp+arg_0], rbx
0x18000a7d5  push    rdi
0x18000a7d6  sub     rsp, 70h
0x18000a7da  mov     rdi, rdx
0x18000a7dd  mov     rbx, rcx
0x18000a7e0  call    ?IsDispatchThread@GameInputDispatcher@@SA_NXZ; GameInputDispatcher::IsDispatchThread(void)
0x18000a7e5  test    al, al
0x18000a7e7  jz      loc_18000A904
0x18000a7ed  mov     rax, [rbx+18h]
0x18000a7f1  nop
0x18000a7f2  test    rax, rax
0x18000a7f5  jz      loc_18000A8F5
0x18000a7fb  cmp     [rax+70h], rdi
0x18000a7ff  jnz     loc_18000A8F5
0x18000a805  nop
0x18000a806  mov     qword ptr [rbx+18h], 0
0x18000a80e  mfence
0x18000a811  lea     rcx, [rbx+30h]
0x18000a815  mov     rdx, [rcx]
0x18000a818  cmp     [rdx+8], rcx
0x18000a81c  jz      short loc_18000A825
0x18000a81e  mov     ecx, 3
0x18000a823  int     29h; Win8: RtlFailFast(ecx)
0x18000a825  mov     [rax], rdx
0x18000a828  mov     [rax+8], rcx
0x18000a82c  mov     [rdx+8], rax
0x18000a830  inc     dword ptr [rcx+10h]
0x18000a833  mov     [rcx], rax
0x18000a836  nop
0x18000a837  mov     dword ptr [rbx+50h], 0
0x18000a83e  mfence
0x18000a841  mov     eax, cs:dword_180069000
0x18000a847  cmp     eax, 4
0x18000a84a  jbe     loc_18000A8F5
0x18000a850  mov     rcx, cs:qword_180069018
0x18000a857  mov     rax, cs:qword_180069010
0x18000a85e  test    al, 1
0x18000a860  jz      loc_18000A8F5
0x18000a866  mov     rax, rcx
0x18000a869  and     eax, 1
0x18000a86c  cmp     rax, rcx
0x18000a86f  jnz     loc_18000A8F5
0x18000a875  mov     rcx, [rbx+20h]
0x18000a879  lea     rdx, qword_180059668
0x18000a880  movzx   eax, word ptr [rcx+6]
0x18000a884  mov     [rsp+78h+arg_10], ax
0x18000a88c  movzx   eax, word ptr [rcx+4]
0x18000a890  mov     [rsp+78h+arg_18], ax
0x18000a898  lea     rax, aDeviceDisconne; "Device disconnected"
0x18000a89f  mov     [rsp+78h+var_20], rax
0x18000a8a4  lea     rax, aOnecoreXboxGam_49; "onecore\\xbox\\gameinput\\client\\GameI"...
0x18000a8ab  mov     [rsp+78h+var_18], rax
0x18000a8b0  lea     rax, [rsp+78h+arg_10]
0x18000a8b8  mov     [rsp+78h+var_38], rax
0x18000a8bd  lea     rax, [rsp+78h+arg_18]
0x18000a8c5  mov     [rsp+78h+var_40], rax
0x18000a8ca  lea     rax, [rsp+78h+var_20]
0x18000a8cf  mov     [rsp+78h+var_48], rax
0x18000a8d4  lea     rax, [rsp+78h+var_28]
0x18000a8d9  mov     [rsp+78h+var_50], rax
0x18000a8de  lea     rax, [rsp+78h+var_18]
0x18000a8e3  mov     [rsp+78h+var_58], rax
0x18000a8e8  mov     [rsp+78h+var_28], 96h
0x18000a8f0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$01@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$01@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<2>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<2> const &)
0x18000a8f5  mov     rbx, [rsp+78h+arg_0]
0x18000a8fd  add     rsp, 70h
0x18000a901  pop     rdi
0x18000a902  retn
0x18000a904  mov     edx, 89h
0x18000a909  mov     ecx, 8000FFFFh
0x18000a90e  call    GameInputFailFast
```
