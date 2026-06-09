# A2dpAptXAdaptiveCodec::GetDiscoveredConfigurationAndSetAsCurrent(_AVDTP_CATEGORY_HEADER * *,uint &)

- ea: `0x140039c10`
- end: `0x140039e67`
- name: `?GetDiscoveredConfigurationAndSetAsCurrent@A2dpAptXAdaptiveCodec@@UEAAJPEAPEAU_AVDTP_CATEGORY_HEADER@@AEAI@Z`
- size: `599`
- prototype: `__int64 __fastcall(A2dpAptXAdaptiveCodec *__hidden this, struct _AVDTP_CATEGORY_HEADER **, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x140003530`
- `0x1400396a4`
- `0x140039918`
- `0x140039c10`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140039d5f`
- `ntoskrnl!ExAllocatePool2` at `0x140039d5f`

## pseudocode

```c
__int64 __fastcall A2dpAptXAdaptiveCodec::GetDiscoveredConfigurationAndSetAsCurrent(
        A2dpAptXAdaptiveCodec *this,
        struct _AVDTP_CATEGORY_HEADER **a2,
        unsigned int *a3)
{
  unsigned int *v3; // r15
  struct _AVDTP_CATEGORY_HEADER **v4; // r14
  char v6; // bl
  __int64 v8; // rbp
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdi
  unsigned int v12; // ebx
  _OWORD *v13; // rax
  _BYTE v14[48]; // [rsp+50h] [rbp-58h] BYREF
  __int64 Pool2; // [rsp+B8h] [rbp+10h] BYREF

  v3 = a3;
  v4 = a2;
  v6 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      14,
      (__int64)WPP_eb459d5104e43cf4a439870cab001d50_Traceguids,
      (char)this);
  }
  if ( !v4 )
    return 3221225485LL;
  if ( *((_BYTE *)this + 16) )
  {
    v8 = *(_BYTE *)(*((_QWORD *)this + 14) + 4LL) != 0 ? 46 : 44;
    Pool2 = ExAllocatePool2(64, v8, 1128354882);
    v11 = Pool2;
    if ( Pool2 )
    {
      v13 = (_OWORD *)A2dpAptXAdaptiveCodec::CurrentHeader(this, v14);
      *(_OWORD *)v11 = *v13;
      *(_OWORD *)(v11 + 16) = v13[1];
      *(_OWORD *)(v11 + 28) = *(_OWORD *)((char *)v13 + 28);
      if ( *(_BYTE *)(*((_QWORD *)this + 14) + 4LL) )
      {
        *(_BYTE *)(v11 + 44) = 8;
        *((_BYTE *)this + 120) = 1;
      }
      *v4 = (struct _AVDTP_CATEGORY_HEADER *)v11;
      v12 = 0;
      *v3 = v8;
      Pool2 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v6 = 0;
      }
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = v6;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v9,
          v10,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          5,
          16,
          (__int64)WPP_eb459d5104e43cf4a439870cab001d50_Traceguids,
          (char)this);
      }
      v12 = -1073741670;
    }
    wil::details::unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&void ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&void ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>(
      &Pool2,
      v9,
      v10);
    return v12;
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v6 = 0;
    }
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = v6;
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)a2,
        (_DWORD)a3,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        15,
        (__int64)WPP_eb459d5104e43cf4a439870cab001d50_Traceguids,
        (char)this);
    }
    return 3221225860LL;
  }
}

```

## disassembly

```asm
0x140039c10  mov     [rsp+arg_0], rbx
0x140039c15  mov     [rsp+arg_10], rbp
0x140039c1a  push    rsi
0x140039c1b  push    rdi
0x140039c1c  push    r13
0x140039c1e  push    r14
0x140039c20  push    r15
0x140039c22  sub     rsp, 80h
0x140039c29  mov     r15, r8
0x140039c2c  mov     r14, rdx
0x140039c2f  mov     rsi, rcx
0x140039c32  mov     rcx, cs:WPP_GLOBAL_Control
0x140039c39  lea     r9, WPP_GLOBAL_Control
0x140039c40  mov     bl, 1
0x140039c42  mov     r13d, 10h
0x140039c48  cmp     rcx, r9
0x140039c4b  jz      short loc_140039C5F
0x140039c4d  mov     eax, [rcx+2Ch]
0x140039c50  test    r13b, al
0x140039c53  jz      short loc_140039C5F
0x140039c55  cmp     byte ptr [rcx+29h], 4
0x140039c59  jb      short loc_140039C5F
0x140039c5b  mov     dl, bl
0x140039c5d  jmp     short loc_140039C61
0x140039c5f  xor     dl, dl
0x140039c61  lea     r10, WPP_RECORDER_INITIALIZED
0x140039c68  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x140039c6f  lea     r11, WPP_eb459d5104e43cf4a439870cab001d50_Traceguids
0x140039c76  setnz   r8b
0x140039c7a  test    dl, dl
0x140039c7c  jnz     short loc_140039C83
0x140039c7e  test    r8b, r8b
0x140039c81  jz      short loc_140039CC3
0x140039c83  mov     r9, [rcx+40h]
0x140039c87  mov     rcx, [rcx+18h]
0x140039c8b  mov     [rsp+0A8h+var_68], rsi
0x140039c90  mov     [rsp+0A8h+var_70], r11
0x140039c95  mov     [rsp+0A8h+var_78], 0Eh
0x140039c9c  mov     [rsp+0A8h+var_80], 5
0x140039ca4  mov     [rsp+0A8h+var_88], 4
0x140039ca9  call    WPP_RECORDER_AND_TRACE_SF_q
0x140039cae  lea     r9, WPP_GLOBAL_Control
0x140039cb5  lea     r10, WPP_RECORDER_INITIALIZED
0x140039cbc  lea     r11, WPP_eb459d5104e43cf4a439870cab001d50_Traceguids
0x140039cc3  test    r14, r14
0x140039cc6  jnz     short loc_140039CD2
0x140039cc8  mov     eax, 0C000000Dh
0x140039ccd  jmp     loc_140039E4A
0x140039cd2  cmp     byte ptr [rsi+10h], 0
0x140039cd6  jnz     short loc_140039D3F
0x140039cd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140039cdf  cmp     rcx, r9
0x140039ce2  jz      short loc_140039CF2
0x140039ce4  mov     eax, [rcx+2Ch]
0x140039ce7  test    r13b, al
0x140039cea  jz      short loc_140039CF2
0x140039cec  cmp     byte ptr [rcx+29h], 2
0x140039cf0  jnb     short loc_140039CF4
0x140039cf2  xor     bl, bl
0x140039cf4  cmp     cs:WPP_RECORDER_INITIALIZED, r10
0x140039cfb  setnz   r8b
0x140039cff  test    bl, bl
0x140039d01  jnz     short loc_140039D08
0x140039d03  test    r8b, r8b
0x140039d06  jz      short loc_140039D35
0x140039d08  mov     r9, [rcx+40h]
0x140039d0c  mov     dl, bl
0x140039d0e  mov     rcx, [rcx+18h]
0x140039d12  mov     [rsp+0A8h+var_68], rsi
0x140039d17  mov     [rsp+0A8h+var_70], r11
0x140039d1c  mov     [rsp+0A8h+var_78], 0Fh
0x140039d23  mov     [rsp+0A8h+var_80], 5
0x140039d2b  mov     [rsp+0A8h+var_88], 2
0x140039d30  call    WPP_RECORDER_AND_TRACE_SF_q
0x140039d35  mov     eax, 0C0000184h
0x140039d3a  jmp     loc_140039E4A
0x140039d3f  mov     rax, [rsi+70h]
0x140039d43  mov     r8d, 43415442h
0x140039d49  mov     cl, [rax+4]
0x140039d4c  neg     cl
0x140039d4e  mov     ecx, 40h ; '@'
0x140039d53  sbb     eax, eax
0x140039d55  and     eax, 2
0x140039d58  add     eax, 2Ch ; ','
0x140039d5b  mov     edx, eax
0x140039d5d  mov     ebp, eax
0x140039d5f  call    cs:__imp_ExAllocatePool2
0x140039d66  nop     dword ptr [rax+rax+00h]
0x140039d6b  mov     [rsp+0A8h+arg_8], rax
0x140039d73  mov     rdi, rax
0x140039d76  test    rax, rax
0x140039d79  jnz     short loc_140039DF3
0x140039d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140039d82  lea     rax, WPP_GLOBAL_Control
0x140039d89  cmp     rcx, rax
0x140039d8c  jz      short loc_140039D9C
0x140039d8e  mov     eax, [rcx+2Ch]
0x140039d91  test    r13b, al
0x140039d94  jz      short loc_140039D9C
0x140039d96  cmp     byte ptr [rcx+29h], 2
0x140039d9a  jnb     short loc_140039D9E
0x140039d9c  xor     bl, bl
0x140039d9e  lea     rax, WPP_RECORDER_INITIALIZED
0x140039da5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140039dac  setnz   r8b
0x140039db0  test    bl, bl
0x140039db2  jnz     short loc_140039DB9
0x140039db4  test    r8b, r8b
0x140039db7  jz      short loc_140039DEC
0x140039db9  mov     r9, [rcx+40h]
0x140039dbd  lea     rax, WPP_eb459d5104e43cf4a439870cab001d50_Traceguids
0x140039dc4  mov     rcx, [rcx+18h]
0x140039dc8  mov     dl, bl
0x140039dca  mov     [rsp+0A8h+var_68], rsi
0x140039dcf  mov     [rsp+0A8h+var_70], rax
0x140039dd4  mov     [rsp+0A8h+var_78], r13w
0x140039dda  mov     [rsp+0A8h+var_80], 5
0x140039de2  mov     [rsp+0A8h+var_88], 2
0x140039de7  call    WPP_RECORDER_AND_TRACE_SF_q
0x140039dec  mov     ebx, 0C000009Ah
0x140039df1  jmp     short loc_140039E3B
0x140039df3  lea     rdx, [rsp+0A8h+var_58]
0x140039df8  mov     rcx, rsi
0x140039dfb  call    ?CurrentHeader@A2dpAptXAdaptiveCodec@@IEBA?AU_CATEGORY_CODEC_APTX_ADAPTIVE@@XZ; A2dpAptXAdaptiveCodec::CurrentHeader(void)
0x140039e00  movups  xmm0, xmmword ptr [rax]
0x140039e03  movups  xmmword ptr [rdi], xmm0
0x140039e06  movups  xmm1, xmmword ptr [rax+10h]
0x140039e0a  movups  xmmword ptr [rdi+10h], xmm1
0x140039e0e  movups  xmm0, xmmword ptr [rax+1Ch]
0x140039e12  movups  xmmword ptr [rdi+1Ch], xmm0
0x140039e16  mov     rax, [rsi+70h]
0x140039e1a  cmp     byte ptr [rax+4], 0
0x140039e1e  jz      short loc_140039E27
0x140039e20  mov     byte ptr [rdi+2Ch], 8
0x140039e24  mov     [rsi+78h], bl
0x140039e27  mov     [r14], rdi
0x140039e2a  xor     ebx, ebx
0x140039e2c  mov     [r15], ebp
0x140039e2f  mov     [rsp+0A8h+arg_8], 0
0x140039e3b  lea     rcx, [rsp+0A8h+arg_8]
0x140039e43  call    ??1?$unique_storage@U?$resource_policy@PEAU_AVDTP_CATEGORY_HEADER@@P6AXPEAX@Z$1?ExFreePool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>(void)
0x140039e48  mov     eax, ebx
0x140039e4a  lea     r11, [rsp+0A8h+var_28]
0x140039e52  mov     rbx, [r11+30h]
0x140039e56  mov     rbp, [r11+40h]
0x140039e5a  mov     rsp, r11
0x140039e5d  pop     r15
0x140039e5f  pop     r14
0x140039e61  pop     r13
0x140039e63  pop     rdi
0x140039e64  pop     rsi
0x140039e65  retn
```
