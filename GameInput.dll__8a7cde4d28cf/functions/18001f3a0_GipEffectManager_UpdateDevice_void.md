# GipEffectManager::UpdateDevice(void)

- ea: `0x18001f3a0`
- end: `0x18001f4bf`
- name: `?UpdateDevice@GipEffectManager@@UEAA_KXZ`
- size: `287`
- prototype: `unsigned __int64 __fastcall(GipEffectManager *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x18000d658`
- `0x180010688`
- `0x180018c14`
- `0x180019328`
- `0x18001947c`
- `0x180019650`
- `0x18001974c`
- `0x18001f3a0`
- `0x18004d010`

## pseudocode

```c
unsigned __int64 __fastcall GipEffectManager::UpdateDevice(GipEffectManager *this, __int64 a2)
{
  unsigned __int64 v3; // rbp
  __int64 v4; // r8
  char *v6; // rbx
  GipEffectManager **v7; // rdi
  GipEffectManager *v8; // rax
  unsigned int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // r9
  unsigned int v12; // eax
  GipEffectManager *v13; // rax
  char v14; // [rsp+60h] [rbp+8h] BYREF

  v3 = GameInputCurrentTime(this, a2);
  if ( !*((_DWORD *)this + 174) )
  {
    if ( (int)GipEffectManager::PreallocateMessageBuffers(this) < 0 )
      return v3 + 100000;
    GipEffectManager::QueueStateMessage(this, v3);
    GipEffectManager::QueueMasterGainMessage(this);
    GipEffectManager::QueueDataMessages(this);
    GipEffectManager::QueueCodeMessages(this);
    GipEffectManager::QueueStateMessage(this, v3);
    if ( !*((_DWORD *)this + 174) )
      return -1;
  }
  v6 = (char *)this + 680;
  v7 = (GipEffectManager **)*((_QWORD *)this + 85);
  if ( v7[1] != (GipEffectManager *)((char *)this + 680) )
    goto LABEL_15;
  v8 = *v7;
  if ( *((GipEffectManager ***)*v7 + 1) != v7 )
    goto LABEL_15;
  *(_QWORD *)v6 = v8;
  *((_QWORD *)v8 + 1) = v6;
  if ( v7 == (GipEffectManager **)v6 )
    v7 = 0;
  else
    --*((_DWORD *)this + 174);
  v9 = *((unsigned __int8 *)v7 + 16);
  v10 = *((_QWORD *)this + 1);
  v11 = *((unsigned __int8 *)v7 + 17);
  LOBYTE(v4) = (_BYTE)v7[2] & 0x1F;
  v14 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64))(*(_QWORD *)v10 + 48LL))(
          v10,
          v9 >> 5,
          v4,
          v11,
          (__int64)v7 + 18);
  if ( (unsigned __int8)GipEffectManager::UpdateDevice_::_1_::_lambda_1_::operator()(&v14, v12) )
  {
    v13 = *(GipEffectManager **)v6;
    if ( *(char **)(*(_QWORD *)v6 + 8LL) == v6 )
    {
      *v7 = v13;
      v7[1] = (GipEffectManager *)v6;
      *((_QWORD *)v13 + 1) = v7;
      ++*((_DWORD *)this + 174);
      *(_QWORD *)v6 = v7;
      return v3 + 100000;
    }
LABEL_15:
    __fastfail(3u);
  }
  if ( *((_DWORD *)this + 174) )
    return 0;
  else
    return -1;
}

```

## disassembly

```asm
0x18001f3a0  push    rbx
0x18001f3a2  push    rbp
0x18001f3a3  push    rsi
0x18001f3a4  push    rdi
0x18001f3a5  sub     rsp, 38h
0x18001f3a9  mov     rsi, rcx
0x18001f3ac  call    GameInputCurrentTime
0x18001f3b1  cmp     dword ptr [rsi+2B8h], 0
0x18001f3b8  mov     rbp, rax
0x18001f3bb  jnz     short loc_18001F410
0x18001f3bd  mov     rcx, rsi; this
0x18001f3c0  call    ?PreallocateMessageBuffers@GipEffectManager@@AEAAJXZ; GipEffectManager::PreallocateMessageBuffers(void)
0x18001f3c5  test    eax, eax
0x18001f3c7  jns     short loc_18001F3D5
0x18001f3c9  lea     rax, [rbp+186A0h]
0x18001f3d0  jmp     loc_18001F4B5
0x18001f3d5  mov     rdx, rbp; unsigned __int64
0x18001f3d8  mov     rcx, rsi; this
0x18001f3db  call    ?QueueStateMessage@GipEffectManager@@AEAAX_K@Z; GipEffectManager::QueueStateMessage(unsigned __int64)
0x18001f3e0  mov     rcx, rsi; this
0x18001f3e3  call    ?QueueMasterGainMessage@GipEffectManager@@AEAAXXZ; GipEffectManager::QueueMasterGainMessage(void)
0x18001f3e8  mov     rcx, rsi; this
0x18001f3eb  call    ?QueueDataMessages@GipEffectManager@@AEAAXXZ; GipEffectManager::QueueDataMessages(void)
0x18001f3f0  mov     rcx, rsi; this
0x18001f3f3  call    ?QueueCodeMessages@GipEffectManager@@AEAAXXZ; GipEffectManager::QueueCodeMessages(void)
0x18001f3f8  mov     rdx, rbp; unsigned __int64
0x18001f3fb  mov     rcx, rsi; this
0x18001f3fe  call    ?QueueStateMessage@GipEffectManager@@AEAAX_K@Z; GipEffectManager::QueueStateMessage(unsigned __int64)
0x18001f403  cmp     dword ptr [rsi+2B8h], 0
0x18001f40a  jz      loc_18001F4B1
0x18001f410  lea     rbx, [rsi+2A8h]
0x18001f417  mov     rdi, [rbx]
0x18001f41a  cmp     [rdi+8], rbx
0x18001f41e  jnz     loc_18001F4AA
0x18001f424  mov     rax, [rdi]
0x18001f427  cmp     [rax+8], rdi
0x18001f42b  jnz     short loc_18001F4AA
0x18001f42d  mov     [rbx], rax
0x18001f430  mov     [rax+8], rbx
0x18001f434  cmp     rdi, rbx
0x18001f437  jz      short loc_18001F43E
0x18001f439  dec     dword ptr [rbx+10h]
0x18001f43c  jmp     short loc_18001F440
0x18001f43e  xor     edi, edi
0x18001f440  movzx   edx, byte ptr [rdi+10h]
0x18001f444  lea     r10, [rdi+12h]
0x18001f448  mov     rcx, [rsi+8]
0x18001f44c  mov     r8b, dl
0x18001f44f  movzx   r9d, byte ptr [rdi+11h]
0x18001f454  and     r8b, 1Fh
0x18001f458  mov     [rsp+58h+arg_0], 0
0x18001f45d  shr     edx, 5
0x18001f460  mov     rax, [rcx]
0x18001f463  mov     [rsp+58h+var_38], r10
0x18001f468  mov     rax, [rax+30h]
0x18001f46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f471  mov     edx, eax
0x18001f473  lea     rcx, [rsp+58h+arg_0]
0x18001f478  call    _GipEffectManager__UpdateDevice____1____lambda_1___operator__
0x18001f47d  test    al, al
0x18001f47f  jz      short loc_18001F4A0
0x18001f481  mov     rax, [rbx]
0x18001f484  cmp     [rax+8], rbx
0x18001f488  jnz     short loc_18001F4AA
0x18001f48a  mov     [rdi], rax
0x18001f48d  mov     [rdi+8], rbx
0x18001f491  mov     [rax+8], rdi
0x18001f495  inc     dword ptr [rbx+10h]
0x18001f498  mov     [rbx], rdi
0x18001f49b  jmp     loc_18001F3C9
0x18001f4a0  cmp     dword ptr [rbx+10h], 0
0x18001f4a4  jz      short loc_18001F4B1
0x18001f4a6  xor     eax, eax
0x18001f4a8  jmp     short loc_18001F4B5
0x18001f4aa  mov     ecx, 3
0x18001f4af  int     29h; Win8: RtlFailFast(ecx)
0x18001f4b1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f4b5  add     rsp, 38h
0x18001f4b9  pop     rdi
0x18001f4ba  pop     rsi
0x18001f4bb  pop     rbp
0x18001f4bc  pop     rbx
0x18001f4bd  retn
```
