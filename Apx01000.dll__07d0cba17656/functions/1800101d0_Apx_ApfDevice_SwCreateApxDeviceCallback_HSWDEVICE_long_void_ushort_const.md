# Apx::ApfDevice::SwCreateApxDeviceCallback(HSWDEVICE__ *,long,void *,ushort const *)

- ea: `0x1800101d0`
- end: `0x180010370`
- name: `?SwCreateApxDeviceCallback@ApfDevice@Apx@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z`
- size: `416`
- prototype: `void __fastcall(struct HSWDEVICE__ *, int, unsigned __int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002160`
- `0x18000a12c`
- `0x18000a1b4`
- `0x18000c7ec`
- `0x18000d2f0`
- `0x1800101d0`

## pseudocode

```c
void __fastcall Apx::ApfDevice::SwCreateApxDeviceCallback(
        struct HSWDEVICE__ *a1,
        int a2,
        unsigned __int64 a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rcx
  _WORD *v8; // rax
  __int64 v9; // rdx
  _WORD *v10; // rcx
  struct Apx::ApfWorkItemBase *v11; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  if ( a2 >= 0 && a4 )
  {
    v7 = 2147483646;
    v8 = (_WORD *)(a3 + 850);
    v9 = 261;
    do
    {
      if ( !v7 )
        break;
      if ( !*a4 )
        break;
      *v8++ = *a4++;
      --v7;
      --v9;
    }
    while ( v9 );
    v10 = v8 - 1;
    if ( v9 )
      v10 = v8;
    *v10 = 0;
    if ( v9 )
    {
      *(_DWORD *)(a3 + 32) |= 0x10u;
      v11 = (struct Apx::ApfWorkItemBase *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v11 )
      {
        *((_QWORD *)v11 + 1) = a3;
        *(_QWORD *)v11 = &Apx::ApfDevice_ReadyProcess::`vftable';
        if ( (int)Apx::ApfWorkItemQueue::AddWorkItemToQueue((Apx::ApfWorkItemQueue *)(a3 + 208), v11) < 0 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 28) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = 42;
LABEL_24:
            WPP_SF_d(v12[2], v13, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
          }
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 41;
          goto LABEL_24;
        }
      }
    }
  }
  imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~a3);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
}

```

## disassembly

```asm
0x1800101d0  mov     [rsp+arg_0], rbx
0x1800101d5  mov     [rsp+arg_8], rbp
0x1800101da  push    rsi
0x1800101db  push    rdi
0x1800101dc  push    r15
0x1800101de  sub     rsp, 30h
0x1800101e2  mov     rbx, r9
0x1800101e5  mov     rdi, r8
0x1800101e8  mov     esi, edx
0x1800101ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800101f1  lea     r15, WPP_GLOBAL_Control
0x1800101f8  cmp     rcx, r15
0x1800101fb  jz      short loc_18001021E
0x1800101fd  test    byte ptr [rcx+1Ch], 1
0x180010201  jz      short loc_18001021E
0x180010203  cmp     byte ptr [rcx+19h], 5
0x180010207  jb      short loc_18001021E
0x180010209  mov     rcx, [rcx+10h]
0x18001020d  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x180010214  mov     edx, 28h ; '('
0x180010219  call    WPP_SF_
0x18001021e  xor     ebp, ebp
0x180010220  test    esi, esi
0x180010222  js      loc_18001030E
0x180010228  test    rbx, rbx
0x18001022b  jz      loc_18001030E
0x180010231  mov     ecx, 7FFFFFFEh
0x180010236  lea     rax, [rdi+352h]
0x18001023d  mov     edx, 105h
0x180010242  test    rcx, rcx
0x180010245  jz      short loc_180010266
0x180010247  movzx   r8d, word ptr [rbx]
0x18001024b  test    r8w, r8w
0x18001024f  jz      short loc_180010266
0x180010251  mov     [rax], r8w
0x180010255  add     rbx, 2
0x180010259  add     rax, 2
0x18001025d  dec     rcx
0x180010260  sub     rdx, 1
0x180010264  jnz     short loc_180010242
0x180010266  test    rdx, rdx
0x180010269  lea     rcx, [rax-2]
0x18001026d  cmovnz  rcx, rax
0x180010271  mov     [rcx], bp
0x180010274  jz      loc_18001030E
0x18001027a  mov     ecx, 10h; unsigned __int64
0x18001027f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010286  or      [rdi+20h], ecx
0x180010289  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001028e  mov     [rsp+48h+arg_10], rax
0x180010293  test    rax, rax
0x180010296  jz      short loc_1800102DB
0x180010298  lea     rcx, ??_7ApfDevice_ReadyProcess@Apx@@6B@; const Apx::ApfDevice_ReadyProcess::`vftable'
0x18001029f  mov     [rax+8], rdi
0x1800102a3  mov     [rax], rcx
0x1800102a6  mov     rdx, rax; struct Apx::ApfWorkItemBase *
0x1800102a9  lea     rcx, [rdi+0D0h]; this
0x1800102b0  call    ?AddWorkItemToQueue@ApfWorkItemQueue@Apx@@QEAAJPEAVApfWorkItemBase@2@@Z; Apx::ApfWorkItemQueue::AddWorkItemToQueue(Apx::ApfWorkItemBase *)
0x1800102b5  test    eax, eax
0x1800102b7  jns     short loc_18001030E
0x1800102b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102c0  cmp     rcx, r15
0x1800102c3  jz      short loc_18001030E
0x1800102c5  test    byte ptr [rcx+1Ch], 80h
0x1800102c9  jz      short loc_18001030E
0x1800102cb  cmp     byte ptr [rcx+19h], 2
0x1800102cf  jb      short loc_18001030E
0x1800102d1  mov     edx, 2Ah ; '*'
0x1800102d6  mov     r9d, eax
0x1800102d9  jmp     short loc_1800102FE
0x1800102db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800102e2  cmp     rcx, r15
0x1800102e5  jz      short loc_18001030E
0x1800102e7  test    byte ptr [rcx+1Ch], 80h
0x1800102eb  jz      short loc_18001030E
0x1800102ed  cmp     byte ptr [rcx+19h], 2
0x1800102f1  jb      short loc_18001030E
0x1800102f3  mov     edx, 29h ; ')'
0x1800102f8  mov     r9d, 8007000Eh
0x1800102fe  mov     rcx, [rcx+10h]
0x180010302  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x180010309  call    WPP_SF_d
0x18001030e  lea     rax, aOnecoreuapDriv_7; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180010315  not     rdi
0x180010318  mov     rdx, rdi; Apx::ApfVerify *
0x18001031b  mov     [rsp+48h+var_28], rax
0x180010320  mov     r9d, 2E4h
0x180010326  xor     r8d, r8d
0x180010329  xor     ecx, ecx; this
0x18001032b  call    imp_ApxObjectDereferenceActual
0x180010330  mov     rcx, cs:WPP_GLOBAL_Control
0x180010337  cmp     rcx, r15
0x18001033a  jz      short loc_18001035D
0x18001033c  test    byte ptr [rcx+1Ch], 1
0x180010340  jz      short loc_18001035D
0x180010342  cmp     byte ptr [rcx+19h], 5
0x180010346  jb      short loc_18001035D
0x180010348  mov     rcx, [rcx+10h]
0x18001034c  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x180010353  mov     edx, 2Bh ; '+'
0x180010358  call    WPP_SF_
0x18001035d  mov     rbx, [rsp+48h+arg_0]
0x180010362  mov     rbp, [rsp+48h+arg_8]
0x180010367  add     rsp, 30h
0x18001036b  pop     r15
0x18001036d  pop     rdi
0x18001036e  pop     rsi
0x18001036f  retn
```
