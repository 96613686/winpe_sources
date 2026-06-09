# CBdeCfgSecureFormat::Thread_WipeAndFormatPartition(void)

- ea: `0x18000d084`
- end: `0x18000d295`
- name: `?Thread_WipeAndFormatPartition@CBdeCfgSecureFormat@@AEAAJXZ`
- size: `529`
- prototype: `__int64 __fastcall(CBdeCfgSecureFormat *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000d780`

## callees

- `0x180007624`
- `0x18000d084`
- `0x18000d510`
- `0x18001358e`
- `0x1800135c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CBdeCfgSecureFormat::Thread_WipeAndFormatPartition(CBdeCfgSecureFormat *this)
{
  int VolumeNameFromPartitionNumber; // ebx
  unsigned __int64 v3; // r8
  __int64 v5; // [rsp+58h] [rbp-2F0h] BYREF
  int v6; // [rsp+60h] [rbp-2E8h] BYREF
  __int64 v7; // [rsp+68h] [rbp-2E0h] BYREF
  _OWORD v8[2]; // [rsp+70h] [rbp-2D8h] BYREF
  _BYTE v9[8]; // [rsp+90h] [rbp-2B8h] BYREF
  unsigned int v10; // [rsp+98h] [rbp-2B0h]
  unsigned __int64 v11; // [rsp+A8h] [rbp-2A0h]
  unsigned __int16 v12[264]; // [rsp+120h] [rbp-228h] BYREF

  v6 = 0;
  v7 = 0;
  memset(v8, 0, sizeof(v8));
  v5 = 0;
  memset_0(v9, 0, 0x90u);
  memset_0(v12, 0, 0x208u);
  VolumeNameFromPartitionNumber = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 5))(
                                    *((_QWORD *)this + 5),
                                    &IID_IVdsAdvancedDisk,
                                    &v5);
  if ( VolumeNameFromPartitionNumber >= 0 )
  {
    VolumeNameFromPartitionNumber = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v5 + 24LL))(
                                      v5,
                                      *((_QWORD *)this + 6),
                                      v9);
    if ( VolumeNameFromPartitionNumber >= 0 )
    {
      VolumeNameFromPartitionNumber = BdeCfgGetVolumeNameFromPartitionNumber(
                                        *((struct IVdsDisk **)this + 5),
                                        v10,
                                        v3,
                                        v12);
      if ( VolumeNameFromPartitionNumber >= 0 )
      {
        VolumeNameFromPartitionNumber = CBdeCfgSecureFormat::Wipe(this, v12, v11);
        if ( VolumeNameFromPartitionNumber >= 0 )
        {
          if ( *((_BYTE *)this + 16) )
          {
            VolumeNameFromPartitionNumber = -1063256047;
          }
          else
          {
            VolumeNameFromPartitionNumber = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, const OLECHAR *, _DWORD, int, int, _DWORD, __int64 *))(*(_QWORD *)v5 + 88LL))(
                                              v5,
                                              *((_QWORD *)this + 6),
                                              4,
                                              &word_180017638,
                                              0,
                                              1,
                                              1,
                                              0,
                                              &v7);
            if ( VolumeNameFromPartitionNumber >= 0 )
            {
              VolumeNameFromPartitionNumber = (*(__int64 (__fastcall **)(__int64, int *, _OWORD *))(*(_QWORD *)v7 + 32LL))(
                                                v7,
                                                &v6,
                                                v8);
              if ( VolumeNameFromPartitionNumber >= 0 )
              {
                if ( v6 >= 0 )
                  *((_DWORD *)this + 3) = 100;
                else
                  VolumeNameFromPartitionNumber = v6;
              }
            }
          }
        }
      }
    }
  }
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v5 = 0;
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)VolumeNameFromPartitionNumber;
}

```

## disassembly

```asm
0x18000d084  mov     [rsp+arg_8], rbx
0x18000d089  push    rdi
0x18000d08a  sub     rsp, 340h
0x18000d091  mov     rax, cs:__security_cookie
0x18000d098  xor     rax, rsp
0x18000d09b  mov     [rsp+348h+var_18], rax
0x18000d0a3  mov     rdi, rcx
0x18000d0a6  mov     [rsp+348h+var_2E8], 0
0x18000d0ae  mov     [rsp+348h+var_2E0], 0
0x18000d0b7  xorps   xmm0, xmm0
0x18000d0ba  movups  [rsp+348h+var_2D8], xmm0
0x18000d0bf  movups  [rsp+348h+var_2C8], xmm0
0x18000d0c7  mov     [rsp+348h+var_2F0], 0
0x18000d0d0  xor     edx, edx; Val
0x18000d0d2  mov     r8d, 90h; Size
0x18000d0d8  lea     rcx, [rsp+348h+var_2B8]; void *
0x18000d0e0  call    memset_0
0x18000d0e5  xor     edx, edx; Val
0x18000d0e7  mov     r8d, 208h; Size
0x18000d0ed  lea     rcx, [rsp+348h+var_228]; void *
0x18000d0f5  call    memset_0
0x18000d0fa  nop
0x18000d0fb  mov     rcx, [rdi+28h]
0x18000d0ff  mov     rax, [rcx]
0x18000d102  lea     r8, [rsp+348h+var_2F0]
0x18000d107  lea     rdx, IID_IVdsAdvancedDisk
0x18000d10e  mov     rax, [rax]
0x18000d111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d116  mov     ebx, eax
0x18000d118  mov     [rsp+348h+var_2F8], eax
0x18000d11c  test    eax, eax
0x18000d11e  js      loc_18000D23D
0x18000d124  mov     rcx, [rsp+348h+var_2F0]
0x18000d129  mov     rax, [rcx]
0x18000d12c  lea     r8, [rsp+348h+var_2B8]
0x18000d134  mov     rdx, [rdi+30h]
0x18000d138  mov     rax, [rax+18h]
0x18000d13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d141  mov     ebx, eax
0x18000d143  mov     [rsp+348h+var_2F8], eax
0x18000d147  test    eax, eax
0x18000d149  js      loc_18000D23D
0x18000d14f  lea     r9, [rsp+348h+var_228]; unsigned __int16 *
0x18000d157  mov     edx, [rsp+348h+var_2B0]; unsigned int
0x18000d15e  mov     rcx, [rdi+28h]; struct IVdsDisk *
0x18000d162  call    ?BdeCfgGetVolumeNameFromPartitionNumber@@YAJPEAUIVdsDisk@@K_KPEAG@Z; BdeCfgGetVolumeNameFromPartitionNumber(IVdsDisk *,ulong,unsigned __int64,ushort *)
0x18000d167  mov     ebx, eax
0x18000d169  mov     [rsp+348h+var_2F8], eax
0x18000d16d  test    eax, eax
0x18000d16f  js      loc_18000D23D
0x18000d175  mov     r8, [rsp+348h+var_2A0]; unsigned __int64
0x18000d17d  lea     rdx, [rsp+348h+var_228]; unsigned __int16 *
0x18000d185  mov     rcx, rdi; this
0x18000d188  call    ?Wipe@CBdeCfgSecureFormat@@AEAAJPEAG_K@Z; CBdeCfgSecureFormat::Wipe(ushort *,unsigned __int64)
0x18000d18d  mov     ebx, eax
0x18000d18f  mov     [rsp+348h+var_2F8], eax
0x18000d193  test    eax, eax
0x18000d195  js      loc_18000D23D
0x18000d19b  mov     al, [rdi+10h]
0x18000d19e  test    al, al
0x18000d1a0  jz      short loc_18000D1B0
0x18000d1a2  mov     ebx, 0C0A00011h
0x18000d1a7  mov     [rsp+348h+var_2F8], ebx
0x18000d1ab  jmp     loc_18000D23D
0x18000d1b0  mov     rcx, [rsp+348h+var_2F0]
0x18000d1b5  mov     rax, [rcx]
0x18000d1b8  lea     rdx, [rsp+348h+var_2E0]
0x18000d1bd  mov     [rsp+348h+var_308], rdx
0x18000d1c2  mov     [rsp+348h+var_310], 0
0x18000d1ca  mov     edx, 1
0x18000d1cf  mov     [rsp+348h+var_318], edx
0x18000d1d3  mov     [rsp+348h+var_320], edx
0x18000d1d7  mov     [rsp+348h+var_328], 0
0x18000d1df  lea     r9, word_180017638
0x18000d1e6  lea     r8d, [rdx+3]
0x18000d1ea  mov     rdx, [rdi+30h]
0x18000d1ee  mov     rax, [rax+58h]
0x18000d1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1f7  mov     ebx, eax
0x18000d1f9  mov     [rsp+348h+var_2F8], eax
0x18000d1fd  test    eax, eax
0x18000d1ff  js      short loc_18000D23D
0x18000d201  mov     rcx, [rsp+348h+var_2E0]
0x18000d206  mov     rax, [rcx]
0x18000d209  lea     r8, [rsp+348h+var_2D8]
0x18000d20e  lea     rdx, [rsp+348h+var_2E8]
0x18000d213  mov     rax, [rax+20h]
0x18000d217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d21c  mov     ebx, eax
0x18000d21e  mov     [rsp+348h+var_2F8], eax
0x18000d222  test    eax, eax
0x18000d224  js      short loc_18000D23D
0x18000d226  mov     eax, [rsp+348h+var_2E8]
0x18000d22a  test    eax, eax
0x18000d22c  jns     short loc_18000D236
0x18000d22e  mov     ebx, eax
0x18000d230  mov     [rsp+348h+var_2F8], eax
0x18000d234  jmp     short loc_18000D23D
0x18000d236  mov     dword ptr [rdi+0Ch], 64h ; 'd'
0x18000d23d  mov     rcx, [rsp+348h+var_2F0]
0x18000d242  test    rcx, rcx
0x18000d245  jz      short loc_18000D25C
0x18000d247  mov     rax, [rcx]
0x18000d24a  mov     rax, [rax+10h]
0x18000d24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d253  mov     [rsp+348h+var_2F0], 0
0x18000d25c  mov     rcx, [rsp+348h+var_2E0]
0x18000d261  test    rcx, rcx
0x18000d264  jz      short loc_18000D272
0x18000d266  mov     rax, [rcx]
0x18000d269  mov     rax, [rax+10h]
0x18000d26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d272  mov     eax, ebx
0x18000d274  mov     rcx, [rsp+348h+var_18]
0x18000d27c  xor     rcx, rsp; StackCookie
0x18000d27f  call    __security_check_cookie
0x18000d284  mov     rbx, [rsp+348h+arg_8]
0x18000d28c  add     rsp, 340h
0x18000d293  pop     rdi
0x18000d294  retn
0x18001415f  push    rbp
0x180014161  sub     rsp, 50h
0x180014165  mov     rbp, rdx
0x180014168  mov     rcx, [rbp+58h]
0x18001416c  test    rcx, rcx
0x18001416f  jz      short loc_180014185
0x180014171  mov     rax, [rcx]
0x180014174  mov     rax, [rax+10h]
0x180014178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001417d  mov     qword ptr [rbp+58h], 0
0x180014185  mov     rcx, [rbp+68h]
0x180014189  test    rcx, rcx
0x18001418c  jz      short loc_18001419B
0x18001418e  mov     rax, [rcx]
0x180014191  mov     rax, [rax+10h]
0x180014195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001419a  nop
0x18001419b  add     rsp, 50h
0x18001419f  pop     rbp
0x1800141a0  retn
```
