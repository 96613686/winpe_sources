# Avdtp_impl::GetConfiguration_Rsp(long,void *,_AVDTP_CATEGORY_HEADER const *,ulong,uchar)

- ea: `0x140049e80`
- end: `0x14004a064`
- name: `?GetConfiguration_Rsp@Avdtp_impl@@CAJJPEAXPEBU_AVDTP_CATEGORY_HEADER@@KE@Z`
- size: `484`
- prototype: `__int64 __fastcall(__int64, Avdtp_impl *this, const struct _AVDTP_CATEGORY_HEADER *Src, size_t Size, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004ad18`

## callees

- `0x140006a88`
- `0x140016d48`
- `0x14002d890`
- `0x140049e80`
- `0x140052804`
- `0x14005ce00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140049fc4`
- `ntoskrnl!ExAllocatePool2` at `0x140049fc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a03d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a03d`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::GetConfiguration_Rsp(
        __int64 a1,
        Avdtp_impl *this,
        const struct _AVDTP_CATEGORY_HEADER *Src,
        size_t Size,
        char a5)
{
  size_t v5; // r14
  int v8; // r13d
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // edi
  struct _SINGLE_PCK_CMD *Pool2; // rax
  struct _SINGLE_PCK_CMD *v13; // rbx
  unsigned int v14; // ebp
  char v15; // al
  _BYTE *v16; // rcx

  v5 = (unsigned int)Size;
  v8 = a1;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(a1, this, Src, Size) )
  {
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        108,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        a5,
        this);
    }
  }
  else
  {
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_L(WPP_GLOBAL_Control->AttachedDevice, v9, v10, WPP_GLOBAL_Control->DeviceExtension, 4);
    }
  }
  if ( !this || !a5 && (!Src || !(_DWORD)v5) )
    return 3221225485LL;
  v11 = 4;
  if ( !a5 )
    v11 = v5 + 2;
  Pool2 = (struct _SINGLE_PCK_CMD *)ExAllocatePool2(64, v11, 1096172628);
  v13 = Pool2;
  if ( Pool2 )
  {
    v15 = *(_BYTE *)Pool2;
    v16 = (char *)v13 + 2;
    v14 = 0;
    if ( a5 )
    {
      v11 = 3;
      *v16 = a5;
      *(_BYTE *)v13 = v15 | 3;
    }
    else
    {
      *(_BYTE *)v13 = v15 & 0xFC | 2;
      memmove(v16, Src, v5);
    }
    Avdtp_impl::CompleteHeaderAndSendSignal(this, v13, 0, v8, 4, *(_BYTE *)v13 & 3, v11);
    ExFreePoolWithTag(v13, 0x41564454u);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v14;
}

```

## disassembly

```asm
0x140049e80  push    rbx
0x140049e82  push    rbp
0x140049e83  push    rsi
0x140049e84  push    rdi
0x140049e85  push    r12
0x140049e87  push    r13
0x140049e89  push    r14
0x140049e8b  push    r15
0x140049e8d  sub     rsp, 58h
0x140049e91  mov     r14d, r9d
0x140049e94  mov     r12, r8
0x140049e97  mov     r15, rdx
0x140049e9a  mov     r13d, ecx
0x140049e9d  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140049ea2  movzx   esi, [rsp+98h+arg_20]
0x140049eaa  test    eax, eax
0x140049eac  jz      short loc_140049F2B
0x140049eae  mov     rcx, cs:WPP_GLOBAL_Control
0x140049eb5  lea     rax, WPP_GLOBAL_Control
0x140049ebc  cmp     rcx, rax
0x140049ebf  jz      short loc_140049ED2
0x140049ec1  mov     eax, [rcx+2Ch]
0x140049ec4  test    al, 8
0x140049ec6  jz      short loc_140049ED2
0x140049ec8  cmp     byte ptr [rcx+29h], 4
0x140049ecc  jb      short loc_140049ED2
0x140049ece  mov     dl, 1
0x140049ed0  jmp     short loc_140049ED4
0x140049ed2  xor     dl, dl
0x140049ed4  lea     rax, WPP_RECORDER_INITIALIZED
0x140049edb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140049ee2  setnz   r8b
0x140049ee6  test    dl, dl
0x140049ee8  jnz     short loc_140049EF3
0x140049eea  test    r8b, r8b
0x140049eed  jz      loc_140049F89
0x140049ef3  mov     r9, [rcx+40h]
0x140049ef7  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x140049efe  mov     rcx, [rcx+18h]
0x140049f02  mov     [rsp+98h+var_50], r15
0x140049f07  mov     [rsp+98h+var_58], esi
0x140049f0b  mov     [rsp+98h+var_60], rax
0x140049f10  mov     word ptr [rsp+98h+var_68], 6Ch ; 'l'
0x140049f17  mov     dword ptr [rsp+98h+var_70], 4
0x140049f1f  mov     [rsp+98h+var_78], 4
0x140049f24  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x140049f29  jmp     short loc_140049F89
0x140049f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140049f32  lea     rax, WPP_GLOBAL_Control
0x140049f39  cmp     rcx, rax
0x140049f3c  jz      short loc_140049F4F
0x140049f3e  mov     eax, [rcx+2Ch]
0x140049f41  test    al, 8
0x140049f43  jz      short loc_140049F4F
0x140049f45  cmp     byte ptr [rcx+29h], 4
0x140049f49  jb      short loc_140049F4F
0x140049f4b  mov     dl, 1
0x140049f4d  jmp     short loc_140049F51
0x140049f4f  xor     dl, dl
0x140049f51  lea     rax, WPP_RECORDER_INITIALIZED
0x140049f58  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140049f5f  setnz   r8b
0x140049f63  test    dl, dl
0x140049f65  jnz     short loc_140049F6C
0x140049f67  test    r8b, r8b
0x140049f6a  jz      short loc_140049F89
0x140049f6c  mov     r9, [rcx+40h]
0x140049f70  mov     rcx, [rcx+18h]
0x140049f74  mov     [rsp+98h+var_58], esi
0x140049f78  mov     word ptr [rsp+98h+var_68], 6Dh ; 'm'
0x140049f7f  mov     [rsp+98h+var_78], 4
0x140049f84  call    WPP_RECORDER_AND_TRACE_SF_L
0x140049f89  test    r15, r15
0x140049f8c  jz      loc_14004A04D
0x140049f92  test    sil, sil
0x140049f95  jnz     short loc_140049FA9
0x140049f97  test    r12, r12
0x140049f9a  jz      loc_14004A04D
0x140049fa0  test    r14d, r14d
0x140049fa3  jz      loc_14004A04D
0x140049fa9  mov     edi, 4
0x140049fae  test    sil, sil
0x140049fb1  jnz     short loc_140049FB7
0x140049fb3  lea     edi, [r14+2]
0x140049fb7  mov     edx, edi
0x140049fb9  mov     ecx, 40h ; '@'
0x140049fbe  mov     r8d, 41564454h
0x140049fc4  call    cs:__imp_ExAllocatePool2
0x140049fcb  nop     dword ptr [rax+rax+00h]
0x140049fd0  mov     rbx, rax
0x140049fd3  test    rax, rax
0x140049fd6  jnz     short loc_140049FDF
0x140049fd8  mov     ebp, 0C000009Ah
0x140049fdd  jmp     short loc_14004A049
0x140049fdf  mov     al, [rax]
0x140049fe1  lea     rcx, [rbx+2]; void *
0x140049fe5  xor     ebp, ebp
0x140049fe7  test    sil, sil
0x140049fea  jnz     short loc_140049FFF
0x140049fec  and     al, 0FEh
0x140049fee  mov     r8, r14; Size
0x140049ff1  or      al, 2
0x140049ff3  mov     rdx, r12; Src
0x140049ff6  mov     [rbx], al
0x140049ff8  call    memmove
0x140049ffd  jmp     short loc_14004A00C
0x140049fff  mov     edi, 3
0x14004a004  mov     [rcx], sil
0x14004a007  or      al, dil
0x14004a00a  mov     [rbx], al
0x14004a00c  mov     r8b, [rbx]
0x14004a00f  mov     r9d, r13d; int
0x14004a012  and     r8b, 3
0x14004a016  mov     ecx, edi
0x14004a018  mov     [rsp+98h+var_68], rcx; unsigned __int64
0x14004a01d  mov     rdx, rbx; struct _SINGLE_PCK_CMD *
0x14004a020  mov     [rsp+98h+var_70], r8b; unsigned __int8
0x14004a025  mov     rcx, r15; this
0x14004a028  xor     r8d, r8d; unsigned __int8
0x14004a02b  mov     [rsp+98h+var_78], 4; char
0x14004a030  call    ?CompleteHeaderAndSendSignal@Avdtp_impl@@AEAAXPEAU_SINGLE_PCK_CMD@@EJEE_K@Z; Avdtp_impl::CompleteHeaderAndSendSignal(_SINGLE_PCK_CMD *,uchar,long,uchar,uchar,unsigned __int64)
0x14004a035  mov     edx, 41564454h; Tag
0x14004a03a  mov     rcx, rbx; P
0x14004a03d  call    cs:__imp_ExFreePoolWithTag
0x14004a044  nop     dword ptr [rax+rax+00h]
0x14004a049  mov     eax, ebp
0x14004a04b  jmp     short loc_14004A052
0x14004a04d  mov     eax, 0C000000Dh
0x14004a052  add     rsp, 58h
0x14004a056  pop     r15
0x14004a058  pop     r14
0x14004a05a  pop     r13
0x14004a05c  pop     r12
0x14004a05e  pop     rdi
0x14004a05f  pop     rsi
0x14004a060  pop     rbp
0x14004a061  pop     rbx
0x14004a062  retn
```
