# A2dpInbandAudioDevice::UpdateChannelsAndSamplerate(int,int)

- ea: `0x14007d1d8`
- end: `0x14007d3b1`
- name: `?UpdateChannelsAndSamplerate@A2dpInbandAudioDevice@@QEAAXHH@Z`
- size: `473`
- prototype: `void __fastcall(A2dpInbandAudioDevice *__hidden this, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x14007a7b0`
- `0x14007cf50`

## callees

- `0x14000f6e4`
- `0x14001027c`
- `0x14001c890`
- `0x14007d1d8`

## import_xrefs

- `ks!KsGetNextSibling` at `0x14007d37b`
- `ks!KsGetNextSibling` at `0x14007d37b`
- `ks!KsGetFirstChild` at `0x14007d35a`
- `ks!KsGetFirstChild` at `0x14007d35a`
- `ks!KsReleaseDevice` at `0x14007d393`
- `ks!KsReleaseDevice` at `0x14007d393`
- `ks!KsAcquireDevice` at `0x14007d1f6`
- `ks!KsAcquireDevice` at `0x14007d1f6`

## pseudocode

```c
void __fastcall A2dpInbandAudioDevice::UpdateChannelsAndSamplerate(PKSDEVICE *this, int a2, int a3)
{
  PDEVICE_OBJECT NextDeviceObject; // rdx
  PKSDEVICE v7; // r9
  _DWORD *v8; // rbx
  int v9; // r8d
  int v10; // r15d
  unsigned int v11; // ecx
  char v12; // bp
  __int64 v13; // rax
  __int64 v14; // rax
  PKSDEVICE v15; // rcx
  struct _KSFILTER *i; // rax
  AVFilter *v17; // rax
  struct _KSFILTER *v18; // rbx
  char v19; // [rsp+40h] [rbp-68h]

  KsAcquireDevice(this[1]);
  v7 = this[3];
  if ( v7 )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v12 = 1;
    while ( v11 < LODWORD(v7->PhysicalDeviceObject) )
    {
      NextDeviceObject = v7->NextDeviceObject;
      v13 = HIDWORD(v7->PhysicalDeviceObject) * v11;
      if ( *(_DWORD *)((char *)&NextDeviceObject->DeviceExtension + v13 + 4) != 4 )
      {
        v14 = *(__int64 *)((char *)&NextDeviceObject->Vpb + v13);
        v8 = *(_DWORD **)v14;
        v9 = *(_DWORD *)(*(_QWORD *)v14 + 64LL);
        v10 = *(_DWORD *)(*(_QWORD *)v14 + 76LL);
        break;
      }
      ++v11;
    }
    if ( a2 != v9 || a3 != v10 )
    {
      LOBYTE(NextDeviceObject) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)NextDeviceObject || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = v9;
        LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_llq(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)NextDeviceObject,
          v9,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          21,
          (__int64)WPP_24d325fae6053930807bc377bc068cf6_Traceguids,
          v19,
          a2,
          (char)this);
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v12 = 0;
      }
      if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(NextDeviceObject) = v12;
        LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_llq(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)NextDeviceObject,
          v9,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          22,
          (__int64)WPP_24d325fae6053930807bc377bc068cf6_Traceguids,
          v10,
          a3,
          (char)this);
      }
      v8[16] = a2;
      v8[19] = a3;
      v8[20] = a3;
      v15 = this[4];
      if ( v15 )
      {
        for ( i = (struct _KSFILTER *)KsGetFirstChild(v15); ; i = (struct _KSFILTER *)KsGetNextSibling(v18) )
        {
          v18 = i;
          if ( !i )
            break;
          v17 = AVFilter::FromKsFilter(i);
          AVFilter::SetFormatChangeEvent(v17);
        }
      }
    }
  }
  KsReleaseDevice(this[1]);
}

```

## disassembly

```asm
0x14007d1d8  push    rbx
0x14007d1da  push    rbp
0x14007d1db  push    rsi
0x14007d1dc  push    rdi
0x14007d1dd  push    r12
0x14007d1df  push    r13
0x14007d1e1  push    r14
0x14007d1e3  push    r15
0x14007d1e5  sub     rsp, 68h
0x14007d1e9  mov     rdi, rcx
0x14007d1ec  mov     esi, r8d
0x14007d1ef  mov     rcx, [rcx+8]; Device
0x14007d1f3  mov     r14d, edx
0x14007d1f6  call    cs:__imp_KsAcquireDevice
0x14007d1fd  nop     dword ptr [rax+rax+00h]
0x14007d202  mov     r9, [rdi+18h]
0x14007d206  test    r9, r9
0x14007d209  jz      loc_14007D38F
0x14007d20f  mov     r10d, [r9+20h]
0x14007d213  xor     ebx, ebx
0x14007d215  xor     r8d, r8d
0x14007d218  xor     r15d, r15d
0x14007d21b  xor     ecx, ecx
0x14007d21d  lea     ebp, [rbx+1]
0x14007d220  cmp     ecx, r10d
0x14007d223  jnb     short loc_14007D24B
0x14007d225  mov     rdx, [r9+28h]
0x14007d229  mov     eax, ecx
0x14007d22b  imul    eax, [r9+24h]
0x14007d230  cmp     dword ptr [rax+rdx+44h], 4
0x14007d235  jnz     short loc_14007D23B
0x14007d237  add     ecx, ebp
0x14007d239  jmp     short loc_14007D220
0x14007d23b  mov     rax, [rax+rdx+38h]
0x14007d240  mov     rbx, [rax]
0x14007d243  mov     r8d, [rbx+40h]
0x14007d247  mov     r15d, [rbx+4Ch]
0x14007d24b  cmp     r14d, r8d
0x14007d24e  jnz     short loc_14007D259
0x14007d250  cmp     esi, r15d
0x14007d253  jz      loc_14007D38F
0x14007d259  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d260  lea     r12, WPP_GLOBAL_Control
0x14007d267  cmp     rcx, r12
0x14007d26a  jz      short loc_14007D27E
0x14007d26c  mov     eax, [rcx+2Ch]
0x14007d26f  test    al, 10h
0x14007d271  jz      short loc_14007D27E
0x14007d273  cmp     byte ptr [rcx+29h], 4
0x14007d277  jb      short loc_14007D27E
0x14007d279  mov     dl, bpl
0x14007d27c  jmp     short loc_14007D280
0x14007d27e  xor     dl, dl
0x14007d280  lea     r13, WPP_RECORDER_INITIALIZED
0x14007d287  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14007d28e  lea     r10, WPP_24d325fae6053930807bc377bc068cf6_Traceguids
0x14007d295  setnz   al
0x14007d298  test    dl, dl
0x14007d29a  jnz     short loc_14007D2A0
0x14007d29c  test    al, al
0x14007d29e  jz      short loc_14007D2DF
0x14007d2a0  mov     r9, [rcx+40h]
0x14007d2a4  mov     rcx, [rcx+18h]
0x14007d2a8  mov     [rsp+0A8h+var_58], rdi
0x14007d2ad  mov     [rsp+0A8h+var_60], r14d
0x14007d2b2  mov     dword ptr [rsp+0A8h+var_68], r8d
0x14007d2b7  mov     r8b, al
0x14007d2ba  mov     [rsp+0A8h+var_70], r10
0x14007d2bf  mov     [rsp+0A8h+var_78], 15h
0x14007d2c6  mov     [rsp+0A8h+var_80], 5
0x14007d2ce  mov     [rsp+0A8h+var_88], 4
0x14007d2d3  call    WPP_RECORDER_AND_TRACE_SF_llq
0x14007d2d8  lea     r10, WPP_24d325fae6053930807bc377bc068cf6_Traceguids
0x14007d2df  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d2e6  cmp     rcx, r12
0x14007d2e9  jz      short loc_14007D2F8
0x14007d2eb  mov     eax, [rcx+2Ch]
0x14007d2ee  test    al, 10h
0x14007d2f0  jz      short loc_14007D2F8
0x14007d2f2  cmp     byte ptr [rcx+29h], 4
0x14007d2f6  jnb     short loc_14007D2FB
0x14007d2f8  xor     bpl, bpl
0x14007d2fb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14007d302  setnz   r8b
0x14007d306  test    bpl, bpl
0x14007d309  jnz     short loc_14007D310
0x14007d30b  test    r8b, r8b
0x14007d30e  jz      short loc_14007D347
0x14007d310  mov     r9, [rcx+40h]
0x14007d314  mov     dl, bpl
0x14007d317  mov     rcx, [rcx+18h]
0x14007d31b  mov     [rsp+0A8h+var_58], rdi
0x14007d320  mov     [rsp+0A8h+var_60], esi
0x14007d324  mov     dword ptr [rsp+0A8h+var_68], r15d
0x14007d329  mov     [rsp+0A8h+var_70], r10
0x14007d32e  mov     [rsp+0A8h+var_78], 16h
0x14007d335  mov     [rsp+0A8h+var_80], 5
0x14007d33d  mov     [rsp+0A8h+var_88], 4
0x14007d342  call    WPP_RECORDER_AND_TRACE_SF_llq
0x14007d347  mov     [rbx+40h], r14d
0x14007d34b  mov     [rbx+4Ch], esi
0x14007d34e  mov     [rbx+50h], esi
0x14007d351  mov     rcx, [rdi+20h]; Object
0x14007d355  test    rcx, rcx
0x14007d358  jz      short loc_14007D38F
0x14007d35a  call    cs:__imp_KsGetFirstChild
0x14007d361  nop     dword ptr [rax+rax+00h]
0x14007d366  jmp     short loc_14007D387
0x14007d368  mov     rcx, rbx; struct _KSFILTER *
0x14007d36b  call    ?FromKsFilter@AVFilter@@SAPEAV1@PEAU_KSFILTER@@@Z; AVFilter::FromKsFilter(_KSFILTER *)
0x14007d370  mov     rcx, rax; this
0x14007d373  call    ?SetFormatChangeEvent@AVFilter@@QEAAXXZ; AVFilter::SetFormatChangeEvent(void)
0x14007d378  mov     rcx, rbx; Object
0x14007d37b  call    cs:__imp_KsGetNextSibling
0x14007d382  nop     dword ptr [rax+rax+00h]
0x14007d387  mov     rbx, rax
0x14007d38a  test    rax, rax
0x14007d38d  jnz     short loc_14007D368
0x14007d38f  mov     rcx, [rdi+8]; Device
0x14007d393  call    cs:__imp_KsReleaseDevice
0x14007d39a  nop     dword ptr [rax+rax+00h]
0x14007d39f  add     rsp, 68h
0x14007d3a3  pop     r15
0x14007d3a5  pop     r14
0x14007d3a7  pop     r13
0x14007d3a9  pop     r12
0x14007d3ab  pop     rdi
0x14007d3ac  pop     rsi
0x14007d3ad  pop     rbp
0x14007d3ae  pop     rbx
0x14007d3af  retn
```
