# CTieredVolume::GetMovementSession(void)

- ea: `0x14000e9a4`
- end: `0x14000ea75`
- name: `?GetMovementSession@CTieredVolume@@QEAAPEAVCSmartTieringMovementSession@1@XZ`
- size: `209`
- prototype: `struct CTieredVolume::CSmartTieringMovementSession *__fastcall(JET_API_PTR ulContext)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140031e04`
- `0x14003ddd4`

## callees

- `0x140001a18`
- `0x14000b7f8`
- `0x14000e9a4`
- `0x14001866c`

## import_xrefs

- `ESENT!JetSetSessionContext` at `0x14000e9bf`
- `ESENT!JetSetSessionContext` at `0x14000e9bf`

## pseudocode

```c
struct CTieredVolume::CSmartTieringMovementSession *__fastcall CTieredVolume::GetMovementSession(JET_API_PTR ulContext)
{
  JET_API_PTR v1; // rdi
  JET_ERR v3; // eax
  struct CTieredVolume::CSmartTieringMovementSession *result; // rax

  v1 = ulContext + 1688;
  v3 = JetSetSessionContext(*(_QWORD *)(ulContext + 1696), ulContext);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        264,
        (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        ulContext + 672,
        v3);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      265,
      (unsigned int)&WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      *(_QWORD *)(ulContext + 1696),
      ulContext + 672);
  }
  result = (struct CTieredVolume::CSmartTieringMovementSession *)operator new(8u);
  if ( !result )
    return 0;
  *(_QWORD *)result = v1;
  return result;
}

```

## disassembly

```asm
0x14000e9a4  mov     [rsp+arg_8], rbx
0x14000e9a9  push    rdi
0x14000e9aa  sub     rsp, 30h
0x14000e9ae  lea     rdi, [rcx+698h]
0x14000e9b5  mov     rbx, rcx
0x14000e9b8  mov     rdx, rcx; ulContext
0x14000e9bb  mov     rcx, [rdi+8]; sesid
0x14000e9bf  call    cs:__imp_JetSetSessionContext
0x14000e9c5  test    eax, eax
0x14000e9c7  jz      short loc_14000EA15
0x14000e9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e9d0  lea     rdx, WPP_GLOBAL_Control
0x14000e9d7  cmp     rcx, rdx
0x14000e9da  jz      short loc_14000EA08
0x14000e9dc  test    byte ptr [rcx+1Ch], 1
0x14000e9e0  jz      short loc_14000EA08
0x14000e9e2  cmp     byte ptr [rcx+19h], 2
0x14000e9e6  jb      short loc_14000EA08
0x14000e9e8  mov     rcx, [rcx+10h]
0x14000e9ec  lea     r9, [rbx+2A0h]
0x14000e9f3  mov     edx, 108h
0x14000e9f8  mov     dword ptr [rsp+38h+var_18], eax
0x14000e9fc  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000ea03  call    WPP_SF_Zd
0x14000ea08  xor     eax, eax
0x14000ea0a  mov     rbx, [rsp+38h+arg_8]
0x14000ea0f  add     rsp, 30h
0x14000ea13  pop     rdi
0x14000ea14  retn
0x14000ea15  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea1c  lea     rdx, WPP_GLOBAL_Control
0x14000ea23  cmp     rcx, rdx
0x14000ea26  jz      short loc_14000EA5C
0x14000ea28  test    byte ptr [rcx+1Ch], 1
0x14000ea2c  jz      short loc_14000EA5C
0x14000ea2e  cmp     byte ptr [rcx+19h], 5
0x14000ea32  jb      short loc_14000EA5C
0x14000ea34  mov     r9, [rbx+6A0h]
0x14000ea3b  lea     rax, [rbx+2A0h]
0x14000ea42  mov     rcx, [rcx+10h]
0x14000ea46  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000ea4d  mov     edx, 109h
0x14000ea52  mov     [rsp+38h+var_18], rax
0x14000ea57  call    WPP_SF_qZ
0x14000ea5c  mov     ecx, 8; Size
0x14000ea61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ea66  mov     [rsp+38h+arg_0], rax
0x14000ea6b  test    rax, rax
0x14000ea6e  jz      short loc_14000EA08
0x14000ea70  mov     [rax], rdi
0x14000ea73  jmp     short loc_14000EA0A
```
