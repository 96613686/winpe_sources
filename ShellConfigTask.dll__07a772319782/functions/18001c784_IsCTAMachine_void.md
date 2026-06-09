# IsCTAMachine(void)

- ea: `0x18001c784`
- end: `0x18001c813`
- name: `?IsCTAMachine@@YA_NXZ`
- size: `143`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ac8c`
- `0x18001b7fc`

## callees

- `0x18000e5b4`
- `0x18001c784`
- `0x180023160`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c7ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c7ff`

## string_xrefs

- `0x18001c7a7`: `Software\Microsoft\Windows\CurrentVersion\DeviceAccess`

## pseudocode

```c
bool IsCTAMachine(void)
{
  bool v0; // di
  int value_nothrow; // eax
  void *v2; // rbx
  int v3; // edx
  bool v5; // [rsp+30h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  pv = 0;
  v0 = 0;
  value_nothrow = wil::reg::get_value_nothrow(
                    HKEY_LOCAL_MACHINE,
                    L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess",
                    L"ActivePolicyCode",
                    &pv);
  v2 = pv;
  if ( value_nothrow >= 0 )
  {
    v3 = *(unsigned __int16 *)pv - 122;
    if ( *(_WORD *)pv == 122 )
    {
      v3 = *((unsigned __int16 *)pv + 1) - 104;
      if ( *((_WORD *)pv + 1) == 104 )
        v3 = *((unsigned __int16 *)pv + 2);
    }
    v0 = v3 == 0;
    v5 = v3 == 0;
  }
  AIXTelemetry::IsCTAMachine<bool &>(&v5);
  if ( v2 )
    CoTaskMemFree(v2);
  return v0;
}

```

## disassembly

```asm
0x18001c784  mov     rax, rsp
0x18001c787  mov     [rax+18h], rbx
0x18001c78b  push    rdi
0x18001c78c  sub     rsp, 20h
0x18001c790  lea     r9, [rax+10h]
0x18001c794  mov     byte ptr [rax+8], 0
0x18001c798  lea     r8, aActivepolicyco; "ActivePolicyCode"
0x18001c79f  mov     qword ptr [rax+10h], 0
0x18001c7a7  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001c7ae  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001c7b5  xor     dil, dil
0x18001c7b8  call    ?get_value_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBG1AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z; wil::reg::get_value_nothrow(HKEY__ *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18001c7bd  mov     rbx, [rsp+28h+pv]
0x18001c7c2  test    eax, eax
0x18001c7c4  js      short loc_18001C7ED
0x18001c7c6  movzx   edx, word ptr [rbx]
0x18001c7c9  sub     edx, 7Ah ; 'z'
0x18001c7cc  jnz     short loc_18001C7E2
0x18001c7ce  movzx   edx, word ptr [rbx+2]
0x18001c7d2  sub     edx, 68h ; 'h'
0x18001c7d5  jnz     short loc_18001C7E2
0x18001c7d7  movzx   edx, word ptr [rbx+4]
0x18001c7db  xor     eax, eax
0x18001c7dd  movzx   ecx, ax
0x18001c7e0  sub     edx, ecx
0x18001c7e2  test    edx, edx
0x18001c7e4  setz    dil
0x18001c7e8  mov     [rsp+28h+arg_0], dil
0x18001c7ed  lea     rcx, [rsp+28h+arg_0]
0x18001c7f2  call    ??$IsCTAMachine@AEA_N@AIXTelemetry@@SAXAEA_N@Z; AIXTelemetry::IsCTAMachine<bool &>(bool &)
0x18001c7f7  test    rbx, rbx
0x18001c7fa  jz      short loc_18001C805
0x18001c7fc  mov     rcx, rbx; pv
0x18001c7ff  call    cs:__imp_CoTaskMemFree
0x18001c805  mov     rbx, [rsp+28h+arg_10]
0x18001c80a  mov     al, dil
0x18001c80d  add     rsp, 20h
0x18001c811  pop     rdi
0x18001c812  retn
```
