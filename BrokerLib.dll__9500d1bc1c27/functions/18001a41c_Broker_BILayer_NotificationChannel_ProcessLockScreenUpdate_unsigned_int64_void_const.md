# Broker::BILayer::NotificationChannel::ProcessLockScreenUpdate(unsigned __int64,void const *)

- ea: `0x18001a41c`
- end: `0x18001a57b`
- name: `?ProcessLockScreenUpdate@NotificationChannel@BILayer@Broker@@QEAAX_KPEBX@Z`
- size: `351`
- prototype: `void __fastcall(Broker::BILayer::NotificationChannel *__hidden this, unsigned __int64, const void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a6e0`

## callees

- `0x18000b120`
- `0x18000c274`
- `0x18001a41c`

## pseudocode

```c
void __fastcall Broker::BILayer::NotificationChannel::ProcessLockScreenUpdate(
        Broker::BILayer::NotificationChannel *this,
        unsigned __int64 a2,
        unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rbx
  Broker::BILayer::NotificationChannel *v4; // r13
  unsigned __int64 v5; // rax
  unsigned int *v6; // r15
  unsigned __int16 *v7; // rcx
  char *v8; // r14
  char *v9; // r12
  __int64 v10; // rsi
  unsigned int i; // edi
  const unsigned __int16 *v12; // r11
  __int64 v13; // r11
  __int64 v14; // rcx
  unsigned __int16 v15; // ax
  char *v16; // [rsp+28h] [rbp-A0h]
  char *v17; // [rsp+30h] [rbp-98h]
  char *v21; // [rsp+40h] [rbp-88h]
  void **v26; // [rsp+60h] [rbp-68h] BYREF
  _DWORD v27[24]; // [rsp+68h] [rbp-60h] BYREF
  unsigned __int16 v28; // [rsp+D8h] [rbp+10h]
  unsigned __int16 v29; // [rsp+E0h] [rbp+18h]

  if ( a2 >= 0x18 )
  {
    v3 = a3;
    v4 = this;
    v5 = a3[10];
    if ( v5 <= a2 )
    {
      v6 = (unsigned int *)a3;
      v7 = a3;
      v8 = (char *)a3 + a2;
      v17 = (char *)a3 + a2;
      v9 = (char *)a3 + v5;
      v21 = (char *)a3 + v5;
      v10 = a3[11];
      for ( i = 0; i < *((_DWORD *)v3 + 4); ++i )
      {
        v12 = (unsigned __int16 *)((char *)v7 + v10);
        if ( (char *)v7 + v10 > v8 )
          break;
        v28 = *v12;
        v29 = *v12;
        v16 = (char *)(v12 + 2);
        if ( (int)RtlStringCbLengthW(v12 + 2, v8 - (char *)(v12 + 2), 0) < 0 )
          break;
        try
        {
          v14 = *((_QWORD *)v4 + 3);
          if ( *(_BYTE *)(v13 + 2) )
          {
            if ( *(_QWORD *)(v14 + 1848) )
              std::_Func_class<void,unsigned long,unsigned short const *,void *>::operator()(
                v14 + 1792,
                *v6,
                v13 + 4,
                v9);
          }
          else if ( *(_QWORD *)(v14 + 2104) )
          {
            std::_Func_class<void,unsigned long,unsigned short const *,void *>::operator()(v14 + 2048, *v6, v16, v9);
          }
        }
        catch ( Broker::Win32Error v26 )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_6d22d7a2e1813c043b7d2163e38154fa_Traceguids, v27[6]);
          v26 = &std::exception::`vftable';
          o___std_exception_destroy_0(v27);
          v8 = v17;
          v3 = a3;
          v9 = v21;
          v6 = (unsigned int *)a3;
          v4 = this;
          v15 = v29;
          goto LABEL_14;
        }
        v15 = v28;
LABEL_14:
        v10 += v15;
        v7 = a3;
      }
    }
  }
}

```

## disassembly

```asm
0x18001a41c  cmp     rdx, 18h
0x18001a420  jb      locret_18001A57A
0x18001a426  push    rbx
0x18001a427  push    rsi
0x18001a428  push    rdi
0x18001a429  push    r12
0x18001a42b  push    r13
0x18001a42d  push    r14
0x18001a42f  push    r15
0x18001a431  sub     rsp, 90h
0x18001a438  mov     rbx, r8
0x18001a43b  mov     r13, rcx
0x18001a43e  movzx   eax, word ptr [r8+14h]
0x18001a443  cmp     rax, rdx
0x18001a446  ja      loc_18001A568
0x18001a44c  mov     [rsp+0C8h+var_90], rbx
0x18001a451  mov     r15, rbx
0x18001a454  mov     [rsp+0C8h+var_78], rcx
0x18001a459  mov     rcx, rbx
0x18001a45c  mov     [rsp+0C8h+var_70], rbx
0x18001a461  lea     r14, [rdx+r8]
0x18001a465  mov     [rsp+0C8h+var_98], r14
0x18001a46a  lea     r12, [rax+r8]
0x18001a46e  mov     [rsp+0C8h+var_88], r12
0x18001a473  movzx   esi, word ptr [r8+16h]
0x18001a478  xor     edi, edi
0x18001a47a  mov     [rsp+0C8h+arg_18], edi
0x18001a481  mov     [rsp+0C8h+var_A8], rsi
0x18001a486  cmp     edi, [rbx+10h]
0x18001a489  jnb     loc_18001A568
0x18001a48f  lea     r11, [rsi+rcx]
0x18001a493  cmp     r11, r14
0x18001a496  ja      loc_18001A568
0x18001a49c  movzx   eax, word ptr [r11]
0x18001a4a0  mov     [rsp+0C8h+arg_8], ax
0x18001a4a8  mov     [rsp+0C8h+arg_10], ax
0x18001a4b0  lea     rax, [r11+4]
0x18001a4b4  mov     [rsp+0C8h+var_A0], rax
0x18001a4b9  mov     rdx, r14
0x18001a4bc  sub     rdx, rax; unsigned __int64
0x18001a4bf  xor     r8d, r8d; unsigned __int64 *
0x18001a4c2  mov     rcx, rax; unsigned __int16 *
0x18001a4c5  call    ?RtlStringCbLengthW@@YAJPEBG_KPEA_K@Z; RtlStringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001a4ca  test    eax, eax
0x18001a4cc  js      loc_18001A568
0x18001a4d2  mov     rcx, [r13+18h]
0x18001a4d6  cmp     byte ptr [r11+2], 0
0x18001a4db  jz      short loc_18001A4FF
0x18001a4dd  cmp     qword ptr [rcx+738h], 0
0x18001a4e5  jz      short loc_18001A521
0x18001a4e7  add     rcx, 700h
0x18001a4ee  mov     r9, r12
0x18001a4f1  lea     r8, [r11+4]
0x18001a4f5  mov     edx, [r15]
0x18001a4f8  call    ??R?$_Func_class@XKPEBGPEAX@std@@QEBAXKPEBGPEAX@Z; std::_Func_class<void,ulong,ushort const *,void *>::operator()(ulong,ushort const *,void *)
0x18001a4fd  jmp     short loc_18001A521
0x18001a4ff  cmp     qword ptr [rcx+838h], 0
0x18001a507  jz      short loc_18001A521
0x18001a509  add     rcx, 800h
0x18001a510  mov     r9, r12
0x18001a513  mov     r8, [rsp+0C8h+var_A0]
0x18001a518  mov     edx, [r15]
0x18001a51b  call    ??R?$_Func_class@XKPEBGPEAX@std@@QEBAXKPEBGPEAX@Z; std::_Func_class<void,ulong,ushort const *,void *>::operator()(ulong,ushort const *,void *)
0x18001a520  nop
0x18001a521  movzx   eax, [rsp+0C8h+arg_8]
0x18001a529  jmp     short loc_18001A556
0x18001a52b  mov     r14, [rsp+0C8h+var_98]
0x18001a530  mov     rsi, [rsp+0C8h+var_A8]
0x18001a535  mov     rbx, [rsp+0C8h+var_90]
0x18001a53a  mov     r12, [rsp+0C8h+var_88]
0x18001a53f  mov     edi, [rsp+0C8h+arg_18]
0x18001a546  mov     r15, rbx
0x18001a549  mov     r13, [rsp+0C8h+var_78]
0x18001a54e  movzx   eax, [rsp+0C8h+arg_10]
0x18001a556  movzx   eax, ax
0x18001a559  add     rsi, rax
0x18001a55c  inc     edi
0x18001a55e  mov     rcx, [rsp+0C8h+var_70]
0x18001a563  jmp     loc_18001A47A
0x18001a568  add     rsp, 90h
0x18001a56f  pop     r15
0x18001a571  pop     r14
0x18001a573  pop     r13
0x18001a575  pop     r12
0x18001a577  pop     rdi
0x18001a578  pop     rsi
0x18001a579  pop     rbx
0x18001a57a  retn
```
