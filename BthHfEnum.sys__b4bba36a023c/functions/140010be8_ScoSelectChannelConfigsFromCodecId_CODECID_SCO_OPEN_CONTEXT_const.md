# ScoSelectChannelConfigsFromCodecId(_CODECID,_SCO_OPEN_CONTEXT const * *)

- ea: `0x140010be8`
- end: `0x140010c7a`
- name: `?ScoSelectChannelConfigsFromCodecId@@YAJW4_CODECID@@PEAPEBU_SCO_OPEN_CONTEXT@@@Z`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000d76c`

## callees

- `0x140010be8`
- `0x140014608`

## pseudocode

```c
__int64 __fastcall ScoSelectChannelConfigsFromCodecId(int a1, __int64 **a2)
{
  int v2; // r8d
  __int64 *v4; // rax

  v2 = a1 - 1;
  if ( a1 == 1 )
  {
    v4 = &qword_14001D3D0;
    goto LABEL_14;
  }
  if ( a1 == 2 )
  {
    v4 = &qword_14001D3B0;
LABEL_14:
    *a2 = v4;
    return 0;
  }
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_CODECID(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      v2,
      WPP_GLOBAL_Control->DeviceExtension);
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140010be8  sub     rsp, 58h
0x140010bec  mov     r8d, ecx
0x140010bef  mov     r9d, ecx
0x140010bf2  sub     r8d, 1
0x140010bf6  jz      short loc_140010C68
0x140010bf8  cmp     r8d, 1
0x140010bfc  jz      short loc_140010C5F
0x140010bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c05  lea     rax, WPP_GLOBAL_Control
0x140010c0c  cmp     rcx, rax
0x140010c0f  jz      short loc_140010C22
0x140010c11  mov     eax, [rcx+2Ch]
0x140010c14  test    al, 10h
0x140010c16  jz      short loc_140010C22
0x140010c18  cmp     byte ptr [rcx+29h], 4
0x140010c1c  jb      short loc_140010C22
0x140010c1e  mov     dl, 1
0x140010c20  jmp     short loc_140010C24
0x140010c22  xor     dl, dl
0x140010c24  lea     rax, WPP_RECORDER_INITIALIZED
0x140010c2b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010c32  setnz   r8b
0x140010c36  test    dl, dl
0x140010c38  jnz     short loc_140010C3F
0x140010c3a  test    r8b, r8b
0x140010c3d  jz      short loc_140010C58
0x140010c3f  mov     [rsp+58h+var_18], r9d
0x140010c44  mov     r9, [rcx+40h]
0x140010c48  mov     rcx, [rcx+18h]
0x140010c4c  mov     [rsp+58h+var_28], 0Ah
0x140010c53  call    WPP_RECORDER_AND_TRACE_SF_CODECID
0x140010c58  mov     eax, 0C000000Dh
0x140010c5d  jmp     short loc_140010C74
0x140010c5f  lea     rax, qword_14001D3B0
0x140010c66  jmp     short loc_140010C6F
0x140010c68  lea     rax, qword_14001D3D0
0x140010c6f  mov     [rdx], rax
0x140010c72  xor     eax, eax
0x140010c74  add     rsp, 58h
0x140010c78  retn
```
