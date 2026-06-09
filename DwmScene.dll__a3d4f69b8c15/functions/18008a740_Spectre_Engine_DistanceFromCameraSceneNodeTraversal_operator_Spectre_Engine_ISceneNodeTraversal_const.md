# Spectre::Engine::DistanceFromCameraSceneNodeTraversal::operator==(Spectre::Engine::ISceneNodeTraversal const &)

- ea: `0x18008a740`
- end: `0x18008a7bf`
- name: `??8DistanceFromCameraSceneNodeTraversal@Engine@Spectre@@UEBA_NAEBVISceneNodeTraversal@12@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18008a740`
- `0x1800d1594`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18008a778`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18008a778`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18008a75e`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18008a76a`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18008a75e`
- `api-ms-win-crt-private-l1-1-0!__RTtypeid` at `0x18008a76a`

## pseudocode

```c
bool __fastcall Spectre::Engine::DistanceFromCameraSceneNodeTraversal::operator==(__int64 a1, __int64 a2)
{
  __int64 v5; // rbx
  __int64 v6; // rax

  if ( a1 == a2 )
    return 1;
  v5 = ((__int64 (*)(void))__RTtypeid)();
  v6 = __RTtypeid(a2);
  return !(unsigned int)__std_type_info_compare(v5 + 8, v6 + 8)
      && *(_DWORD *)(a1 + 8) == *(_DWORD *)(_RTDynamicCast_0(
                                              a2,
                                              0,
                                              &Spectre::Engine::ISceneNodeTraversal `RTTI Type Descriptor',
                                              &Spectre::Engine::DistanceFromCameraSceneNodeTraversal `RTTI Type Descriptor',
                                              1)
                                          + 8);
}

```

## disassembly

```asm
0x18008a740  mov     [rsp+arg_0], rbx
0x18008a745  mov     [rsp+arg_8], rsi
0x18008a74a  push    rdi
0x18008a74b  sub     rsp, 30h
0x18008a74f  mov     rdi, rdx
0x18008a752  mov     rsi, rcx
0x18008a755  cmp     rcx, rdx
0x18008a758  jnz     short loc_18008A75E
0x18008a75a  mov     al, 1
0x18008a75c  jmp     short loc_18008A7AF
0x18008a75e  call    cs:__imp___RTtypeid
0x18008a764  mov     rcx, rdi
0x18008a767  mov     rbx, rax
0x18008a76a  call    cs:__imp___RTtypeid
0x18008a770  lea     rcx, [rbx+8]
0x18008a774  lea     rdx, [rax+8]
0x18008a778  call    cs:__imp___std_type_info_compare
0x18008a77e  test    eax, eax
0x18008a780  jz      short loc_18008A786
0x18008a782  xor     al, al
0x18008a784  jmp     short loc_18008A7AF
0x18008a786  lea     r9, ??_R0?AVDistanceFromCameraSceneNodeTraversal@Engine@Spectre@@@8; Spectre::Engine::DistanceFromCameraSceneNodeTraversal `RTTI Type Descriptor'
0x18008a78d  mov     [rsp+38h+var_18], 1
0x18008a795  lea     r8, ??_R0?AVISceneNodeTraversal@Engine@Spectre@@@8; Spectre::Engine::ISceneNodeTraversal `RTTI Type Descriptor'
0x18008a79c  xor     edx, edx
0x18008a79e  mov     rcx, rdi
0x18008a7a1  call    __RTDynamicCast_0
0x18008a7a6  mov     ecx, [rax+8]
0x18008a7a9  cmp     [rsi+8], ecx
0x18008a7ac  setz    al
0x18008a7af  mov     rbx, [rsp+38h+arg_0]
0x18008a7b4  mov     rsi, [rsp+38h+arg_8]
0x18008a7b9  add     rsp, 30h
0x18008a7bd  pop     rdi
0x18008a7be  retn
```
