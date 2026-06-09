# wil::details::functor_wrapper_void__lambda_dc7b9ad6b6a2994ae091d68eebe8b5ed___::Run

- ea: `0x18002e620`
- end: `0x18002e7f9`
- name: `wil::details::functor_wrapper_void__lambda_dc7b9ad6b6a2994ae091d68eebe8b5ed___::Run`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002c244`

## callees

- `0x1800034a0`
- `0x180010cac`
- `0x1800110fc`
- `0x180011194`
- `0x18002e620`
- `0x18002f2a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002e638`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002e638`
- `deviceassociation!DafStartFinalize` at `0x18002e652`
- `deviceassociation!DafStartFinalize` at `0x18002e652`

## string_xrefs

- `0x18002e760`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002e7e4`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_dc7b9ad6b6a2994ae091d68eebe8b5ed___::Run(__int64 a1)
{
  unsigned int **v1; // rdi
  int v2; // r8d
  unsigned int *v3; // rbx
  int v4; // edx
  int v5; // r8d
  char v6; // dl
  bool v8; // dl
  unsigned int v9; // eax
  unsigned int v10; // eax
  int v11; // [rsp+20h] [rbp-38h]
  int v12; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = *(unsigned int ***)(a1 + 8);
  ResetEvent(*((HANDLE *)*v1 + 256));
  *v1[1] = DafStartFinalize(
             *((_QWORD *)*v1 + 255),
             Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_FinalizeCompleteCallback,
             *v1);
  if ( (*v1[1] & 0x80000000) != 0 )
  {
    v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v2, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v9 = wil::verify_hresult<long>(*v1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E5,
      (int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v9,
      v11);
  }
  v3 = v1[1];
  *v3 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)*v1);
  if ( (*v1[1] & 0x80000000) != 0 )
  {
    LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        v5,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v11,
        v12,
        82,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v10 = wil::verify_hresult<long>(*v1[1]);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2EC,
      (int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v10,
      v11);
  }
  v6 = 1;
  *((_BYTE *)*v1 + 144) = 1;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    v6 = 0;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v5, *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  return 0;
}

```

## disassembly

```asm
0x18002e620  mov     [rsp+arg_0], rbx
0x18002e625  push    rdi
0x18002e626  sub     rsp, 50h
0x18002e62a  mov     rdi, [rcx+8]
0x18002e62e  mov     rcx, [rdi]
0x18002e631  mov     rcx, [rcx+800h]; hEvent
0x18002e638  call    cs:__imp_ResetEvent
0x18002e63e  mov     rcx, [rdi]
0x18002e641  lea     rdx, ?s_FinalizeCompleteCallback@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@CAXW4_DAF_ASSOCIATION_STATUS@@PEAXJ@Z; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::s_FinalizeCompleteCallback(_DAF_ASSOCIATION_STATUS,void *,long)
0x18002e648  mov     r8, rcx
0x18002e64b  mov     rcx, [rcx+7F8h]
0x18002e652  call    cs:__imp_DafStartFinalize
0x18002e658  mov     rcx, [rdi+8]
0x18002e65c  mov     [rcx], eax
0x18002e65e  mov     rax, [rdi+8]
0x18002e662  cmp     dword ptr [rax], 0
0x18002e665  jl      loc_18002E6F6
0x18002e66b  mov     rcx, [rdi]; this
0x18002e66e  mov     rbx, rax
0x18002e671  call    ?WaitForDafQueryEvent@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::WaitForDafQueryEvent(void)
0x18002e676  mov     [rbx], eax
0x18002e678  mov     rax, [rdi+8]
0x18002e67c  mov     r9d, [rax]
0x18002e67f  test    r9d, r9d
0x18002e682  js      loc_18002E775
0x18002e688  mov     rax, [rdi]
0x18002e68b  mov     dl, 1
0x18002e68d  mov     [rax+90h], dl
0x18002e693  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e69a  lea     rax, WPP_GLOBAL_Control
0x18002e6a1  cmp     rcx, rax
0x18002e6a4  jz      short loc_18002E6AC
0x18002e6a6  cmp     byte ptr [rcx+19h], 4
0x18002e6aa  jnb     short loc_18002E6AE
0x18002e6ac  xor     dl, dl
0x18002e6ae  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e6b5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e6bc  setnz   r8b
0x18002e6c0  test    dl, dl
0x18002e6c2  jnz     short loc_18002E6C9
0x18002e6c4  test    r8b, r8b
0x18002e6c7  jz      short loc_18002E6E9
0x18002e6c9  mov     r9, [rcx+28h]
0x18002e6cd  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e6d4  mov     rcx, [rcx+10h]
0x18002e6d8  mov     [rsp+58h+var_20], rax
0x18002e6dd  mov     [rsp+58h+var_28], 53h ; 'S'
0x18002e6e4  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002e6e9  mov     rbx, [rsp+58h+arg_0]
0x18002e6ee  xor     eax, eax
0x18002e6f0  add     rsp, 50h
0x18002e6f4  pop     rdi
0x18002e6f5  retn
0x18002e6f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e6fd  lea     rax, WPP_GLOBAL_Control
0x18002e704  cmp     rcx, rax
0x18002e707  jz      short loc_18002E713
0x18002e709  cmp     byte ptr [rcx+19h], 2
0x18002e70d  jb      short loc_18002E713
0x18002e70f  mov     dl, 1
0x18002e711  jmp     short loc_18002E715
0x18002e713  xor     dl, dl
0x18002e715  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e71c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e723  setnz   r8b
0x18002e727  test    dl, dl
0x18002e729  jnz     short loc_18002E730
0x18002e72b  test    r8b, r8b
0x18002e72e  jz      short loc_18002E750
0x18002e730  mov     r9, [rcx+28h]
0x18002e734  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e73b  mov     rcx, [rcx+10h]
0x18002e73f  mov     [rsp+58h+var_20], rax
0x18002e744  mov     [rsp+58h+var_28], 51h ; 'Q'
0x18002e74b  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002e750  mov     rcx, [rdi+8]
0x18002e754  mov     ecx, [rcx]
0x18002e756  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e75b  mov     rcx, [rsp+58h]; this
0x18002e760  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002e767  mov     r9d, eax; char *
0x18002e76a  mov     edx, 2E5h; void *
0x18002e76f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e775  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e77c  lea     rax, WPP_GLOBAL_Control
0x18002e783  cmp     rcx, rax
0x18002e786  jz      short loc_18002E792
0x18002e788  cmp     byte ptr [rcx+19h], 2
0x18002e78c  jb      short loc_18002E792
0x18002e78e  mov     dl, 1
0x18002e790  jmp     short loc_18002E794
0x18002e792  xor     dl, dl
0x18002e794  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e79b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e7a2  setnz   r8b
0x18002e7a6  test    dl, dl
0x18002e7a8  jnz     short loc_18002E7AF
0x18002e7aa  test    r8b, r8b
0x18002e7ad  jz      short loc_18002E7D4
0x18002e7af  mov     [rsp+58h+var_10], r9d
0x18002e7b4  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e7bb  mov     r9, [rcx+28h]
0x18002e7bf  mov     rcx, [rcx+10h]
0x18002e7c3  mov     [rsp+58h+var_20], rax
0x18002e7c8  mov     [rsp+58h+var_28], 52h ; 'R'
0x18002e7cf  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002e7d4  mov     rcx, [rdi+8]
0x18002e7d8  mov     ecx, [rcx]
0x18002e7da  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e7df  mov     rcx, [rsp+58h]; this
0x18002e7e4  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002e7eb  mov     r9d, eax; char *
0x18002e7ee  mov     edx, 2ECh; void *
0x18002e7f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
