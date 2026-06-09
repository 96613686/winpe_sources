# GameInputModule::ValidateModuleVersion(HINSTANCE__ *,GameInputVersion const &)

- ea: `0x140006a78`
- end: `0x140006b40`
- name: `?ValidateModuleVersion@GameInputModule@@CA_NPEAUHINSTANCE__@@AEBUGameInputVersion@@@Z`
- size: `200`
- prototype: `bool __fastcall(HINSTANCE, const struct GameInputVersion *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140006750`

## callees

- `0x1400066d0`
- `0x140006a78`
- `0x140007750`

## import_xrefs

- `ntdll!LdrResSearchResource` at `0x140006afd`
- `ntdll!LdrResSearchResource` at `0x140006afd`

## pseudocode

```c
bool __fastcall GameInputModule::ValidateModuleVersion(HINSTANCE a1, const struct GameInputVersion *a2)
{
  __int64 v4; // [rsp+40h] [rbp-38h] BYREF
  _QWORD v5[3]; // [rsp+48h] [rbp-30h] BYREF

  if ( GameInputModule::IsXbox() )
    return 1;
  v4 = 0;
  v5[0] = 16;
  v5[1] = 1;
  v5[2] = 0;
  return (int)LdrResSearchResource(a1, v5, 3, 256, &v4, 0, 0, 0) >= 0
      && (*(unsigned int *)(v4 + 52) | ((unsigned __int64)*(unsigned int *)(v4 + 48) << 32)) >= 0x905739F03E8LL;
}

```

## disassembly

```asm
0x140006a78  push    rbx
0x140006a7a  sub     rsp, 70h
0x140006a7e  mov     rax, cs:__security_cookie
0x140006a85  xor     rax, rsp
0x140006a88  mov     [rsp+78h+var_18], rax
0x140006a8d  mov     rbx, rcx
0x140006a90  call    ?IsXbox@GameInputModule@@CA_NXZ; GameInputModule::IsXbox(void)
0x140006a95  test    al, al
0x140006a97  jz      short loc_140006AA0
0x140006a99  mov     al, 1
0x140006a9b  jmp     loc_140006B2D
0x140006aa0  mov     [rsp+78h+var_40], 0
0x140006aa9  lea     rax, [rsp+78h+var_38]
0x140006aae  mov     [rsp+78h+var_48], 0
0x140006ab7  lea     rdx, [rsp+78h+var_30]
0x140006abc  mov     [rsp+78h+var_50], 0
0x140006ac5  mov     r9d, 100h
0x140006acb  mov     r8d, 3
0x140006ad1  mov     [rsp+78h+var_58], rax
0x140006ad6  mov     rcx, rbx
0x140006ad9  mov     [rsp+78h+var_38], 0
0x140006ae2  mov     [rsp+78h+var_30], 10h
0x140006aeb  mov     [rsp+78h+var_28], 1
0x140006af4  mov     [rsp+78h+var_20], 0
0x140006afd  call    cs:__imp_LdrResSearchResource
0x140006b03  test    eax, eax
0x140006b05  js      short loc_140006B2B
0x140006b07  mov     rax, [rsp+78h+var_38]
0x140006b0c  mov     ecx, [rax+30h]
0x140006b0f  mov     eax, [rax+34h]
0x140006b12  shl     rcx, 20h
0x140006b16  or      rcx, rax
0x140006b19  mov     rax, 905739F03E8h
0x140006b23  cmp     rcx, rax
0x140006b26  setnb   al
0x140006b29  jmp     short loc_140006B2D
0x140006b2b  xor     al, al
0x140006b2d  mov     rcx, [rsp+78h+var_18]
0x140006b32  xor     rcx, rsp; StackCookie
0x140006b35  call    __security_check_cookie
0x140006b3a  add     rsp, 70h
0x140006b3e  pop     rbx
0x140006b3f  retn
```
