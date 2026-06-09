# System.Deployment.Application.Logger::Serialize

- ea: `0x17e60`
- end: `0x17edc`
- name: `System.Deployment.Application.Logger::Serialize`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x202a0`

## callees

- `0x17e60`

## string_xrefs

- `0x17e9f`: `, ProxyUri=`

## pseudocode

```c

```

## disassembly

```asm
0x17e60  ldarg.0
0x17e61  brtrue.s loc_17E69
0x17e63  ldstr    asc_2F208// ""
0x17e68  ret
0x17e69  ldarg.0
0x17e6a  callvirt instance class [System]System.Net.IWebProxy [System]System.Net.WebRequest::get_Proxy()
0x17e6f  stloc.0
0x17e70  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x17e75  stloc.1
0x17e76  ldloc.0
0x17e77  brfalse.s loc_17EC9
0x17e79  ldloc.1
0x17e7a  ldstr    aProxyIsbypasse// " Proxy.IsByPassed="
0x17e7f  ldloc.0
0x17e80  ldarg.0
0x17e81  callvirt instance class [System]System.Uri [System]System.Net.WebRequest::get_RequestUri()
0x17e86  callvirt instance bool [System]System.Net.IWebProxy::IsBypassed(class [System]System.Uri)
0x17e8b  stloc.2
0x17e8c  ldloca.s 2
0x17e8e  call     instance string [mscorlib]System.Boolean::ToString()
0x17e93  call     string [mscorlib]System.String::Concat(string, string)
0x17e98  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17e9d  pop
0x17e9e  ldloc.1
0x17e9f  ldstr    aProxyuri// ", ProxyUri="
0x17ea4  ldloc.0
0x17ea5  ldarg.0
0x17ea6  callvirt instance class [System]System.Uri [System]System.Net.WebRequest::get_RequestUri()
0x17eab  callvirt instance class [System]System.Uri [System]System.Net.IWebProxy::GetProxy(class [System]System.Uri)
0x17eb0  dup
0x17eb1  brtrue.s loc_17EB7
0x17eb3  pop
0x17eb4  ldnull
0x17eb5  br.s     loc_17EBC
0x17eb7  callvirt instance string [mscorlib]System.Object::ToString()
0x17ebc  call     string [mscorlib]System.String::Concat(string, string)
0x17ec1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17ec6  pop
0x17ec7  br.s     loc_17ED5
0x17ec9  ldloc.1
0x17eca  ldstr    aNoProxySet// " No proxy set."
0x17ecf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x17ed4  pop
0x17ed5  ldloc.1
0x17ed6  callvirt instance string [mscorlib]System.Object::ToString()
0x17edb  ret
```
