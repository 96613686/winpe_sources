# CSyncServices::Initialize(_ID_PARAMETERS const *)

- ea: `0x180020540`
- end: `0x180020681`
- name: `?Initialize@CSyncServices@@UEAAJPEBU_ID_PARAMETERS@@@Z`
- size: `321`
- prototype: `int(CSyncServices *__hidden this, const struct _ID_PARAMETERS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002d220`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x180020540`
- `0x180020688`

## string_xrefs

- `0x180020634`: `CSyncServices::Initialize`
- `0x180020663`: `CSyncServices::Initialize`

## pseudocode

```c
__int64 __fastcall CSyncServices::Initialize(CSyncServices *this, const struct _ID_PARAMETERS *a2)
{
  PVOID *v4; // r10
  unsigned int v5; // ebx
  _WORD *v6; // rax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::Initialize");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)this + 6) )
  {
    v5 = -2147217407;
  }
  else
  {
    v5 = -2147217408;
    if ( (unsigned int)IdParameters::ValidParameters(a2) )
    {
      v5 = -2147024882;
      v6 = SeAlloc(0x38u);
      if ( v6 )
      {
        v5 = 0;
        *(_DWORD *)v6 = a2->replicaId.fIsVariable;
        v6[2] = a2->replicaId.cbIdSize;
        *((_QWORD *)v6 + 1) = 0;
        *((_DWORD *)v6 + 4) = a2->itemId.fIsVariable;
        v6[10] = a2->itemId.cbIdSize;
        *((_QWORD *)v6 + 3) = 0;
        *((_DWORD *)v6 + 8) = a2->changeUnitId.fIsVariable;
        v6[18] = a2->changeUnitId.cbIdSize;
        *((_QWORD *)v6 + 5) = 0;
        *((_DWORD *)v6 + 12) = 1;
        *((_QWORD *)v6 + 1) = v6;
        *((_QWORD *)v6 + 3) = v6;
        *((_QWORD *)v6 + 5) = v6;
        *((_QWORD *)this + 6) = v6;
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      15,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::Initialize",
      v5);
  return v5;
}

```

## disassembly

```asm
0x180020540  push    rbx
0x180020542  push    rsi
0x180020543  push    rdi
0x180020544  push    r14
0x180020546  sub     rsp, 38h
0x18002054a  mov     rdi, rdx
0x18002054d  mov     rsi, rcx
0x180020550  mov     r10, cs:WPP_GLOBAL_Control
0x180020557  lea     r14, WPP_GLOBAL_Control
0x18002055e  cmp     r10, r14
0x180020561  jnz     loc_18002061A
0x180020567  cmp     qword ptr [rsi+30h], 0
0x18002056c  jnz     loc_180020613
0x180020572  mov     rcx, rdi; struct _ID_PARAMETERS *
0x180020575  mov     ebx, 80041000h
0x18002057a  call    ?ValidParameters@IdParameters@@SAHPEBU_ID_PARAMETERS@@@Z; IdParameters::ValidParameters(_ID_PARAMETERS const *)
0x18002057f  test    eax, eax
0x180020581  jz      short loc_1800205FB
0x180020583  mov     ecx, 38h ; '8'; unsigned __int64
0x180020588  mov     ebx, 8007000Eh
0x18002058d  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180020592  mov     rdx, rax
0x180020595  test    rax, rax
0x180020598  jz      short loc_1800205F4
0x18002059a  mov     ecx, [rdi+4]
0x18002059d  xor     ebx, ebx
0x18002059f  mov     [rax], ecx
0x1800205a1  movzx   ecx, word ptr [rdi+8]
0x1800205a5  mov     [rax+4], cx
0x1800205a9  mov     qword ptr [rax+8], 0
0x1800205b1  mov     ecx, [rdi+0Ch]
0x1800205b4  mov     [rax+10h], ecx
0x1800205b7  movzx   eax, word ptr [rdi+10h]
0x1800205bb  mov     [rdx+14h], ax
0x1800205bf  mov     qword ptr [rdx+18h], 0
0x1800205c7  mov     eax, [rdi+14h]
0x1800205ca  mov     [rdx+20h], eax
0x1800205cd  movzx   eax, word ptr [rdi+18h]
0x1800205d1  mov     [rdx+24h], ax
0x1800205d5  mov     qword ptr [rdx+28h], 0
0x1800205dd  mov     dword ptr [rdx+30h], 1
0x1800205e4  mov     [rdx+8], rdx
0x1800205e8  mov     [rdx+18h], rdx
0x1800205ec  mov     [rdx+28h], rdx
0x1800205f0  mov     [rsi+30h], rdx
0x1800205f4  mov     r10, cs:WPP_GLOBAL_Control
0x1800205fb  cmp     r10, r14
0x1800205fe  jz      short loc_180020607
0x180020600  test    byte ptr [r10+1Ch], 2
0x180020605  jnz     short loc_180020658
0x180020607  mov     eax, ebx
0x180020609  add     rsp, 38h
0x18002060d  pop     r14
0x18002060f  pop     rdi
0x180020610  pop     rsi
0x180020611  pop     rbx
0x180020612  retn
0x180020613  mov     ebx, 80041001h
0x180020618  jmp     short loc_1800205FB
0x18002061a  test    byte ptr [r10+1Ch], 2
0x18002061f  jz      loc_180020567
0x180020625  cmp     byte ptr [r10+19h], 5
0x18002062a  jb      loc_180020567
0x180020630  mov     rcx, [r10+10h]
0x180020634  lea     r9, aCsyncservicesI; "CSyncServices::Initialize"
0x18002063b  mov     edx, 0Eh
0x180020640  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x180020647  call    WPP_SF_s
0x18002064c  mov     r10, cs:WPP_GLOBAL_Control
0x180020653  jmp     loc_180020567
0x180020658  cmp     byte ptr [r10+19h], 5
0x18002065d  jb      short loc_180020607
0x18002065f  mov     rcx, [r10+10h]
0x180020663  lea     r9, aCsyncservicesI; "CSyncServices::Initialize"
0x18002066a  mov     edx, 0Fh
0x18002066f  mov     [rsp+58h+var_38], ebx
0x180020673  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002067a  call    WPP_SF_sD
0x18002067f  jmp     short loc_180020607
```
