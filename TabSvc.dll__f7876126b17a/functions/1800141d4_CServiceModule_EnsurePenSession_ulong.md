# CServiceModule::EnsurePenSession(ulong)

- ea: `0x1800141d4`
- end: `0x1800142a7`
- name: `?EnsurePenSession@CServiceModule@@QEAAPEAVCPenSession@@K@Z`
- size: `211`
- prototype: `struct CPenSession *__fastcall(CServiceModule *this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001506c`
- `0x180023f54`
- `0x180024260`

## callees

- `0x1800141d4`
- `0x1800142b0`
- `0x18002b3a8`
- `0x18002b404`

## string_xrefs

- `0x180014206`: `PENSERVICE_CServiceModule::EnsurePenSession`
- `0x18001427c`: `PENSERVICE_CServiceModule::EnsurePenSession`

## pseudocode

```c
struct CPenSession *__fastcall CServiceModule::EnsurePenSession(CServiceModule *this, int a2)
{
  struct _GUID *v4; // r10
  __int64 i; // rdx
  __int64 v6; // rax
  __int64 v7; // r8
  struct CPenSession *v8; // rbx
  struct CPenSession *PenSession; // rax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      36,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::EnsurePenSession",
      a2);
    v4 = WPP_GLOBAL_Control;
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 71); i = (unsigned int)(i + 1) )
  {
    v6 = *((_QWORD *)this + 34);
    v7 = *(_QWORD *)(v6 + 8 * i);
    if ( v7 && *(_DWORD *)(v7 + 4) == a2 )
    {
      if ( (_DWORD)i != -1 )
      {
        v8 = *(struct CPenSession **)(v6 + 8 * i);
        goto LABEL_12;
      }
      break;
    }
  }
  PenSession = CServiceModule::CreatePenSession(this, a2);
  v4 = WPP_GLOBAL_Control;
  v8 = PenSession;
LABEL_12:
  if ( v4 != (struct _GUID *)&WPP_GLOBAL_Control && (v4[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v4[1].Data1,
      37,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::EnsurePenSession");
  return v8;
}

```

## disassembly

```asm
0x1800141d4  mov     [rsp+arg_0], rbx
0x1800141d9  mov     [rsp+arg_8], rsi
0x1800141de  push    rdi
0x1800141df  sub     rsp, 30h
0x1800141e3  mov     edi, edx
0x1800141e5  mov     rbx, rcx
0x1800141e8  mov     r10, cs:WPP_GLOBAL_Control
0x1800141ef  lea     rsi, WPP_GLOBAL_Control
0x1800141f6  cmp     r10, rsi
0x1800141f9  jz      short loc_180014229
0x1800141fb  test    byte ptr [r10+1Ch], 10h
0x180014200  jz      short loc_180014229
0x180014202  mov     rcx, [r10+10h]
0x180014206  lea     r9, aPenserviceCser_25; "PENSERVICE_CServiceModule::EnsurePenSes"...
0x18001420d  mov     edx, 24h ; '$'
0x180014212  mov     [rsp+38h+var_18], edi
0x180014216  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18001421d  call    WPP_SF_sd
0x180014222  mov     r10, cs:WPP_GLOBAL_Control
0x180014229  xor     edx, edx
0x18001422b  cmp     edx, [rbx+11Ch]
0x180014231  jnb     short loc_180014258
0x180014233  mov     rax, [rbx+110h]
0x18001423a  mov     r8, [rax+rdx*8]
0x18001423e  test    r8, r8
0x180014241  jz      short loc_180014249
0x180014243  cmp     [r8+4], edi
0x180014247  jz      short loc_18001424D
0x180014249  inc     edx
0x18001424b  jmp     short loc_18001422B
0x18001424d  cmp     edx, 0FFFFFFFFh
0x180014250  jz      short loc_180014258
0x180014252  mov     rbx, [rax+rdx*8]
0x180014256  jmp     short loc_18001426C
0x180014258  mov     edx, edi; unsigned int
0x18001425a  mov     rcx, rbx; this
0x18001425d  call    ?CreatePenSession@CServiceModule@@QEAAPEAVCPenSession@@K@Z; CServiceModule::CreatePenSession(ulong)
0x180014262  mov     r10, cs:WPP_GLOBAL_Control
0x180014269  mov     rbx, rax
0x18001426c  cmp     r10, rsi
0x18001426f  jz      short loc_180014294
0x180014271  test    byte ptr [r10+1Ch], 10h
0x180014276  jz      short loc_180014294
0x180014278  mov     rcx, [r10+10h]
0x18001427c  lea     r9, aPenserviceCser_25; "PENSERVICE_CServiceModule::EnsurePenSes"...
0x180014283  mov     edx, 25h ; '%'
0x180014288  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18001428f  call    WPP_SF_s
0x180014294  mov     rsi, [rsp+38h+arg_8]
0x180014299  mov     rax, rbx
0x18001429c  mov     rbx, [rsp+38h+arg_0]
0x1800142a1  add     rsp, 30h
0x1800142a5  pop     rdi
0x1800142a6  retn
```
