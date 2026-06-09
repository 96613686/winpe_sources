# std::_Ref_count_obj2<Com::InterfaceMarshaler<IWpcOtsRequestManager>>::_Ref_count_obj2<Com::InterfaceMarshaler<IWpcOtsRequestManager>>(WpcDesktop::OTS::Manager::WpcOtsRequestManager * const &,Com::MarshalOptions &&)

- ea: `0x18000b5c0`
- end: `0x18000b6d8`
- name: `??$?0AEBQEAVWpcOtsRequestManager@Manager@OTS@WpcDesktop@@W4MarshalOptions@Com@@@?$_Ref_count_obj2@V?$InterfaceMarshaler@UIWpcOtsRequestManager@@@Com@@@std@@QEAA@AEBQEAVWpcOtsRequestManager@Manager@OTS@WpcDesktop@@$$QEAW4MarshalOptions@Com@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c164`

## callees

- `0x1800036e4`
- `0x18000b5c0`
- `0x18000bbac`
- `0x180022a84`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<Com::InterfaceMarshaler<IWpcOtsRequestManager>>::_Ref_count_obj2<Com::InterfaceMarshaler<IWpcOtsRequestManager>>(
        __int64 a1,
        _QWORD *a2,
        unsigned int *a3)
{
  char **v4; // rbx
  __int64 v5; // r9
  __int64 v6; // r8
  __int64 v7; // rdx
  char **v8; // rdi
  char *v9; // rcx
  char *v10; // rax
  _BYTE v12[40]; // [rsp+20h] [rbp-28h] BYREF

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<Com::InterfaceMarshaler<IWpcOtsRequestManager>>::`vftable';
  v4 = (char **)(a1 + 16);
  v5 = *a3;
  v6 = *a2 + 32LL;
  v7 = v6 & ((unsigned __int128)-(__int128)(unsigned __int64)*a2 >> 64);
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  if ( v7 )
  {
    v8 = (char **)Com::MarshalInterface(v12, v7, v6, v5);
    if ( v4 != v8 )
    {
      v9 = *v4;
      if ( *v4 )
      {
        if ( (unsigned __int64)(v4[2] - v9) < 0x1000 )
        {
          v10 = *v4;
        }
        else
        {
          v10 = (char *)*((_QWORD *)v9 - 1);
          if ( (unsigned __int64)(v9 - v10 - 8) > 0x1F )
            __fastfail(5u);
        }
        operator delete(v10);
        *v4 = 0;
        v4[1] = 0;
        v4[2] = 0;
      }
      *v4 = *v8;
      v4[1] = v8[1];
      v4[2] = v8[2];
      *v8 = 0;
      v8[1] = 0;
      v8[2] = 0;
    }
    std::vector<char>::~vector<char>(v12);
  }
  return a1;
}

```

## disassembly

```asm
0x18000b5c0  mov     r11, rsp
0x18000b5c3  mov     [r11+10h], rbx
0x18000b5c7  mov     [r11+18h], rsi
0x18000b5cb  push    rdi
0x18000b5cc  sub     rsp, 40h
0x18000b5d0  mov     rsi, rcx
0x18000b5d3  mov     eax, 1
0x18000b5d8  mov     [rcx+8], eax
0x18000b5db  mov     [rcx+0Ch], eax
0x18000b5de  lea     rax, ??_7?$_Ref_count_obj2@V?$InterfaceMarshaler@UIWpcOtsRequestManager@@@Com@@@std@@6B@; const std::_Ref_count_obj2<Com::InterfaceMarshaler<IWpcOtsRequestManager>>::`vftable'
0x18000b5e5  mov     [rcx], rax
0x18000b5e8  lea     rbx, [rcx+10h]
0x18000b5ec  mov     [r11+8], rbx
0x18000b5f0  mov     r9d, [r8]
0x18000b5f3  mov     rax, [rdx]
0x18000b5f6  lea     r8, [rax+20h]
0x18000b5fa  neg     rax
0x18000b5fd  sbb     rdx, rdx
0x18000b600  and     rdx, r8
0x18000b603  mov     qword ptr [rbx], 0
0x18000b60a  mov     qword ptr [rbx+8], 0
0x18000b612  mov     qword ptr [rbx+10h], 0
0x18000b61a  jz      loc_18000B6C5
0x18000b620  lea     rcx, [r11-28h]
0x18000b624  call    ?MarshalInterface@Com@@YA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIUnknown@@AEBU_GUID@@W4MarshalOptions@1@@Z; Com::MarshalInterface(IUnknown *,_GUID const &,Com::MarshalOptions)
0x18000b629  mov     rdi, rax
0x18000b62c  cmp     rbx, rax
0x18000b62f  jz      loc_18000B6BA
0x18000b635  mov     rcx, [rbx]
0x18000b638  test    rcx, rcx
0x18000b63b  jz      short loc_18000B68D
0x18000b63d  mov     rdx, [rbx+10h]
0x18000b641  sub     rdx, rcx
0x18000b644  cmp     rdx, 1000h
0x18000b64b  jb      short loc_18000B66B
0x18000b64d  mov     rax, [rcx-8]
0x18000b651  sub     rcx, rax
0x18000b654  sub     rcx, 8
0x18000b658  cmp     rcx, 1Fh
0x18000b65c  ja      short loc_18000B664
0x18000b65e  add     rdx, 27h ; '''
0x18000b662  jmp     short loc_18000B66E
0x18000b664  mov     ecx, 5
0x18000b669  int     29h; Win8: RtlFailFast(ecx)
0x18000b66b  mov     rax, rcx
0x18000b66e  mov     rcx, rax; Block
0x18000b671  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b676  mov     qword ptr [rbx], 0
0x18000b67d  mov     qword ptr [rbx+8], 0
0x18000b685  mov     qword ptr [rbx+10h], 0
0x18000b68d  mov     rax, [rdi]
0x18000b690  mov     [rbx], rax
0x18000b693  mov     rax, [rdi+8]
0x18000b697  mov     [rbx+8], rax
0x18000b69b  mov     rax, [rdi+10h]
0x18000b69f  mov     [rbx+10h], rax
0x18000b6a3  mov     qword ptr [rdi], 0
0x18000b6aa  mov     qword ptr [rdi+8], 0
0x18000b6b2  mov     qword ptr [rdi+10h], 0
0x18000b6ba  lea     rcx, [rsp+48h+var_28]
0x18000b6bf  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18000b6c4  nop
0x18000b6c5  mov     rax, rsi
0x18000b6c8  mov     rbx, [rsp+48h+arg_8]
0x18000b6cd  mov     rsi, [rsp+48h+arg_10]
0x18000b6d2  add     rsp, 40h
0x18000b6d6  pop     rdi
0x18000b6d7  retn
```
